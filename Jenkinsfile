pipeline {
    agent {  
        label 'linux-node'  
    }  
    stages {
        stage('Checkout') {  
            steps {  
                git credentialsId: 'ef1f8776-6770-486c-bcbf-22d720b6351a' url: 'https://github.com/RKDAtiles/node-webapp.git', branch: 'main'
            }  
        }  
        stage('Build Docker Image') {
            steps {  
                script {  
                    docker.build('node-webapp:latest')
                }
            }  
        }  
        stage('Run Docker Container') {
            steps {  
                script {  
                    docker.image('node-webapp:latest').run('-d -p 3000:3000')
                }  
            }  
        }
    }  
}
