pipeline{
    agent any
    environment{
	DOCKER_TAG = getDockertag()
    }
    stages{
        stage('construir Iamgen'){
            steps{
                sh "docker build . -t /home/debian/myproyecto/node-app:${DOCKER_TAG}"
            }
        }   
     }
 }
def getDockerTag(){
    def tag  = sh script: 'git rev-parse HEAD', returnStdout: true
    return tag
}

