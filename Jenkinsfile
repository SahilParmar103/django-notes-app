@Library('Shared')_
pipeline{
    agent { label 'dev-server'}
    
    stages{
        stage("Code "){
            steps{
            clone("https://github.com/SahilParmar103/django-notes-app.git","main")
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
