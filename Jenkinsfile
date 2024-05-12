@Library("Shared_lib@master") _
pipeline {
    agent any
    
    stages {
        stage("Clean Workspace"){
            steps{
                script{
                    cleanWs()
                }
            }
        }
        
        stage("Code checkout"){
            steps{
                script{
                    git url: "https://github.com/DevMadhup/node-todo-cicd.git", branch: "master"
                }
            }
        }
        
        stage("Build Docker image"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred', url: 'https://registry.hub.docker.com') {
                        docker_build("node-app","latest","madhupdevops")
                    }   
                }
            }
        }
    }
}
