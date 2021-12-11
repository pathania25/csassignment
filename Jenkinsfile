pipeline { 
    environment { 
        registry = "pathania90/jenkinswithplugin" 
        registryCredential = 'dockerhub' 
        dockerImage = '' 
    }
    agent any 
    stages { 
        stage('Cloning our Git') { 
            steps {
                git 'https://github.com/pathania25/csassignment.git' 
            }
        } 
        stage('Building our image') { 
            steps { 
                script { 
                    dockerImage = docker.build registry + ":$BUILD_NUMBER" 
                }
            } 
        }
        stage('Deploy our image') { 
            steps { 
                script { 
                    docker.withRegistry( '', registryCredential ) { 
                        dockerImage.push() 
                    }
                } 
            }
        } 
        stage('docker stop container') {
             steps{
                sh 'docker ps -f name=jenkinsContainer -q | xargs --no-run-if-empty docker container stop'
                sh 'docker container ls -a -fname=jenkinsContainer -q | xargs -r docker container rm'
             }
        }
    
        stage('Docker Run') {
            steps{
             script{
                dockerImage.run("-p 8080:8080 --rm --name jenkinsContainer")
            }
        }
    }
}
