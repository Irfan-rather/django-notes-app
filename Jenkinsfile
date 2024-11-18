@Library('Shared') _
pipeline{
    agent { label 'vagrant'}
    
    stages{
        stage("Code clone"){
            steps{
            sh "whoami"
            clone("https://github.com/Irfan-rather/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
                script{
            docker.build("notes-app","latest")
            }
        }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                docker.push("dockerHubCreds","notes-app","latest")
            }
        }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
