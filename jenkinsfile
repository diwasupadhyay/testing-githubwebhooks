pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'docker build -t testing .'
            }
        }
        stage('Run') {
            steps {
                bat 'docker stop testing || exit 0'
                bat 'docker rm testing || exit 0'
                bat 'docker run -d --name testing -p 3000:3000 testing'
            }
        }
    }
}
