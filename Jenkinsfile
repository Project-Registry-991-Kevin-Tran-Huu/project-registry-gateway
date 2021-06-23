pipeline {
	environment {
		registry = "devaraj1234/microservice-registry"
		registryCredential = 'docker_hub_id'
		dockerImage = ''
	}	
    agent any
    stages {
       
        stage ('Build Application'){
        	steps {
             	sh 'mvn clean package spring-boot:repackage'
             	}
        	}
        
        stage('Publish Tests Results'){
      		steps {
          		echo "Publish junit Tests Results"
		  		junit '**/target/surefire-reports/TEST-*.xml'
		  		archive 'target/*.jar'
        	}
    	}
    	
    	stage('Build Docker Image') {
      		steps{
 				sh 'docker stop gateway || true && docker rm gateway || true'
 				sh 'docker image rm devaraj1234/microservice-registry:gateway || true'
      			sh 'docker build -t devaraj1234/microservice-registry:gateway .'
      		}
    	}
    	
    	stage('Push Docker Image') {
            steps {
            script {
				docker.withRegistry( '', registryCredential ) {
                	sh 'docker push devaraj1234/microservice-registry:gateway'
                	sh 'docker image rm devaraj1234/microservice-registry:gateway || true'
                	}
               	}
              }
           }
           
        stage('Pull & Run Docker Image') {
        steps{
        	sh 'docker pull devaraj1234/microservice-registry:gateway'
        	sh 'docker run -d --name=gateway --link consul:consul -p 8085:8085 devaraj1234/microservice-registry:gateway'
        }
        
        }
        
    }
}