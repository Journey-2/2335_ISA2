pipeline {
    agent any
    stages {
        stage('Build Image') {
            steps {
                bat 'docker build -t "isa2-image:1.0" .'
            }
        }
        stage('Remove existing container') {
            steps {
                bat 'docker rm -f isa2-container || true'
            }
        }
        stage('Run container') {
            steps {
                bat 'docker run -d --name isa2-container isa2-image:1.0'
            }
        }
    }
}
