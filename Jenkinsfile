pipeline {
    agent any

    environment {
        DEPLOY_DIR = '/Users/vijayendarmenni/deploy'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/vijayendarmenni/test.git', branch: 'main'
            }
        }

        stage('Deploy to Local Directory') {
            steps {
                sh '''
                mkdir -p ${DEPLOY_DIR}
                cp -r * ${DEPLOY_DIR}/
                echo "Deployment Completed to ${DEPLOY_DIR}"
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
