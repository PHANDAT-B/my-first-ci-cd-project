pipeline {
    agent any 
    stages {
        stage("Build and Test Python App") {
            agent {
                docker {
                    image "python:3.12.3-slim"
                }
            }
            steps {
                dir('python-app') {
                    echo '=== Checking python version ==='
                    sh 'python3 --version'

                    echo '=== Installing dependencies ==='
                    sh 'pip install --no-cache-dir -r requirements.txt || true'
                    echo '=== Running Python Application ==='
                    sh 'python main.py'
                    echo 'login feature'
                }
            }
        }
        stage("Build and Test Node.js App") {
            agent {
                docker {
                    image 'node:22-alpine'
                }
            }
            steps {
                dir('node-app') {
                    echo "=== Checking node version ===" 
                    sh 'node --version'

                    echo "=== Installing Node.js dependencies ==="
                    sh 'npm install'

                    echo '=== Running Node.js Application'
                    sh 'npm run start'
                    echo 'Login feature'
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline execution finished!'
        }
        success {
            echo 'Both Python and Node.js application ran successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs'
        }
    }
    
}