pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Nginx server...'
                sh '''
                docker stop mi-nginx-server || true
                docker rm mi-nginx-server || true
                docker run -d -p 8081:80 --name mi-nginx-server nginx
                '''
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}