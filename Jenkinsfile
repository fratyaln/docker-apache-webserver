pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main' url: 'https://github.com/fratyaln/docker-apache-webserver.git'
            }
        }
    stage('Build') {
            steps {
                sh 'docker build -t $img:$IMAGE_TAG .'
            }
        }

    stage('Deploy') {
            steps {
                sh 'docker run -d -p 80:80 --name apache-container $img:$IMAGE_TAG'
            }
        }

   }



     post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed. Please check the logs.'
        } 
       }
}
