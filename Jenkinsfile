pipeline {
    agent any
    
    stages {
        stage("Clean Workspace"){
            cleanWs()
        }
        
        stage("Code checkout"){
            steps{
                git url: "https://github.com/DevMadhup/node-todo-cicd.git", branch: "master"
            }
        }
        
        stage("Build Docker image"){
            steps{
                withDockerRegistry(credentialsId: 'docker-cred', url: 'https://registry.hub.docker.com') {
                sh "docker build -t madhupdevops/node-app-test-new:latest ."
                }   
            }
        }
    }
}
