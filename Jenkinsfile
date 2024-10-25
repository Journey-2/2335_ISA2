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
                bat 'docker rm -f 2335-container || true'
            }
        }
        stage('Run container') {
            steps {
                bat 'docker run -d --name 2335-container isa2-image:1.0'
            }
        } 
    }
}
