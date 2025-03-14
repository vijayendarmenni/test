pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/your-username/test.git'
            }
        }

        stage('Deploy to Local Directory') {
            steps {
                script {
                    def deployPath = '/usr/local/var/www/html'

                    // Ensure deployment directory exists
                    sh "sudo mkdir -p ${deployPath}"

                    // Clear previous deployment
                    sh "sudo rm -rf ${deployPath}/*"

                    // Copy HTML & CSS files
                    sh "sudo cp -r * ${deployPath}/"
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment Successful!'
        }
        failure {
            echo 'Deployment Failed!'
        }
    }
}
