pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/lapis-17/simple-node-js-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t dock-jens .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f mycontainer || true
                docker run -d --name mycontainer -p 3000:3000 dock-jens
                '''
            }
        }
    }
}