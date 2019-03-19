pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'yarn global add serve'
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Serve') {
            steps {
                sh 'serve -s build'
            }
        }
    }
}