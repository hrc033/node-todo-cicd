pipeline {
    agent { label "dev-server"}
    
    stages {
        
        stage("code"){
            steps{
                git url: "https://github.com/LondheShubham153/node-todo-cicd.git", branch: "master"
                echo 'bhaiyya code clone ho gaya'
            }
        }
        stage("build and test"){
            steps{
                sh "docker build -t node-app-test-new ."
                echo 'code build bhi ho gaya'
            }
        }
        stage("scan image"){
            steps{
                echo 'image scanning ho gayi'
            }
        }
        stage("Build"){
            steps{
                withDockerRegistry(credentialsId: 'docker-cred', url: 'https://registry.hub.docker.com') 
                sh "docker build madhupdevops/node-app-test-new:latest"
                echo 'image build ho gaya'
                }
                
            }
        }
}
