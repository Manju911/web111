pipeline {

    agent any

    stages {

        stage('Checkout') {

            steps {
                checkout scm
            }
        }

        stage('Build Maven') {

            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {

            steps {
                sh 'sudo docker build -t manjunath911/webapp1:latest .'
            }
        }

        stage('Docker Push') {

            steps {
                sh 'sudo docker push manjunath911/webapp1:latest'
            }
        }

        stage('Kubernetes Deploy') {

            steps {
                sh 'kubectl apply -f k8s/'
            }
        }
    }
}
