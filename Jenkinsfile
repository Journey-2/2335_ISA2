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
                bat 'docker build -t "ISA2-image:1.0" .'
            }
        }
        stage('Remove existing container') {
            steps {
                bat 'docker rm -f ISA2 || true'
            }
        }
        stage('Run container') {
            steps {
                bat 'docker run -d --name ISA2 ISA2-image:1.0'
            }
        }
    }
    }
