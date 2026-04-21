pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/pradeep08/repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker stop myapp || true'
                sh 'docker rm myapp || true'
                sh 'docker run -d -p 80:5000 --name myapp myapp'
            }
        }
    }
}
