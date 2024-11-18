@Library('Shared') _
pipeline{
    agent { label 'vagrant'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
                sh "pwd"
                sh "hello"
            clone("https:https://github.com/Irfan-rather/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
