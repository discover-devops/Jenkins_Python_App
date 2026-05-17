pipeline {

    agent {
        label 'myslave'
    }

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-flask-demo .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f flask-container || true'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flask-container python-flask-demo'
            }
        }
    }
}
