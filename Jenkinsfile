@Library("Shared_lib@main") _

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
                    code_checkout("https://github.com/DevMadhup/node-todo-cicd.git","master")
                }
            }
        }
        
        stage("Build Docker image"){
            steps{
                script{
                        docker_build("node-app","latest","madhupdevops")  
                }
            }
        }

        stage("Push Docker image"){
            steps{
                script{
                        docker_push("node-app","v1","madhupdevops")  
                }
            }
        }
    }
}
