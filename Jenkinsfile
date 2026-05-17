@Library('shared-library') _
pipeline{
    agent {label 'django1'}

    stages{
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/Ramakantvats/django-notes-app.git", "main")
                }
                
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("django-image", "latest")
                }
            }
        }
        stage("Push"){
            steps{
                script{
                    docker_push()
                }
            }
        }
        stage("Deploy"){
            steps{
                script{
                    deploy()
                }
            }
        }
    }
}
