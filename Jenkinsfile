
@Library('Shared') _
pipeline{
    agent { label 'vagrant'}
    
    stages{
        stage("Code clone"){
            steps{
                script{
            sh "whoami"
            clone("https://github.com/Irfan-rather/django-notes-app.git","main")
            }
        }
        }
        stage("Code Build"){
            steps{
                script{
            docker_build( "notes-app", "latest", "irfan845" )
            }
        }
        }
        stage("Push to DockerHub"){
            steps{
                script{
               docker_push("notes-app","latest","irfan845")
            }
        }
        }
        stage("Deploy"){
            steps{
                script{
        
                docker_deploy()
                   
            }
        }
        
    }
}
}
