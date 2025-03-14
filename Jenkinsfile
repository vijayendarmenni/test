pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/vijayendarmenni/test.git', branch: 'main'
            }
        }

        stage('Deploy to Local Directory') {
            steps {
                sh '''
                mkdir -p /usr/local/var/www/html
                cp -r * /usr/local/var/www/html/
                echo "Deployment Completed!"
                '''
            }
        }
    }

    post {
        failure {
            echo "Deployment Failed!"
        }
        success {
            echo "Deployment Successful!"
        }
    }
}
