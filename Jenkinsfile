pipeline {
    agent any
    
    stages{
        stage("Code"){
            steps{
                git url: "https://github.com/LondheShubham153/django-notes-app.git", branch: "dev"
            }
        }
        stage("Build"){
            steps{
                sh "docker build . -t node-app-test-new"
            }
        }
        stage("Push to DockerHub"){
            steps{
                withCredentials([usernamePassword(credentialsId:"dockerHub",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]){
                    sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                    sh "docker tag node-app-test-new ${env.dockerHubUser}/node-app-test-new:latest"
                    sh "docker push ${env.dockerHubUser}/node-app-test-new:latest" 
                    echo "Login successfull"
                }
            }
        }
        
        stage("Deploy"){
            steps{
                sh "docker run -d -p 8000:8000 ramramji/node-app-test-new:latest"
            }
        }
    }
}