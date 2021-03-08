pipeline{
    agent any
    environment{
	DOCKER_TAG = getDockertag()
    }
    stages{
        stage('construir Iamgen'){
            steps{
                sh "docker build . -t pedrox19766/nodeapp:${DOCKER_TAG}"
            }
        }   
     }
 }

 def getDockertag(){
     def tag = sh script: 'git rev-parse HEAD', returnStdout: true 
     return tag
 }
