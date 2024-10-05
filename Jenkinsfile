pipeline {	
	agent any	tools {	    
		maven 'my-maven’		
		jdk 'my-jdk’	
	}	
	stages {        
		stage('Clone'){			
			steps {git url:'https://github.com/rohitha987/employee-service.git', branch:'main’}			}		
		stage('Build'){			
			steps {bat "mvn clean install -DskipTests"}		
		}		
		stage('Test'){			
			steps{bat "mvn test"}		}		
		}
		stage('Deploy') {			
			steps { bat "docker build -t emp-image ."			    
			            bat "docker run -p 8082:8082 -d --name emp-container emp-image"}		
		}		
	}
}
