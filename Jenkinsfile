jenkinsfile
	pipeline {
		agent any 
		environment{
				DOCKER_TAG=getDockerTag
		 }
		stages{
			stages('Construir la Imagen'){
				steps{
					sh "docker build -t . /home/pedro/proyecto:${DOCKER_TAG}"
				}
			}
			stages('DockerHub Push'){
			     steps{
			    withCredentials([string(credentialsId: 'docler-hub', variable: 'dockerHubPwd')]) {
			    sh "Docker login -u /home/pedro/proyecto -p $(dockerHubPwd)" 
			             sh "docker push /home/pedro/proyecto:${DOCKER_TAG}" 
                     }
                 }
            }
        }
   }	
		

		def getDockerTag(){
				def tag = sh script 'git rev-parse HEAD', returnStdout: true
				return tag 
		}

