pipeline {
    agent any
    stages {
        stage('Clone Github repo') {
            steps {
                bat 'git clone "https://github.com/Journey-2/2335_ISA2.git"'
            }
        }
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
