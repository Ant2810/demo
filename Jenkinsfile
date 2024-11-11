pipeline {
    agent any

    stages {
        stage('Git Stage') {
            steps {
                git branch: 'main', url: 'https://github.com/Ant2810/demo.git'
            }
        }

        stage('Build and Push Docker Image'){
            steps {
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t 21127209/demo .'
                    sh 'docker push 21127209/demo'  
                }
            }
        }
    }
}
