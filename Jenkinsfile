pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/Here2ServeU/docker-nodejs-webapp.git'
            }
        }
        stage('Setup Node.js') {
            steps {
                sh '''
                curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
                sudo apt-get install -y nodejs
                node -v
                npm -v
                '''
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                script {
                    try {
                        sh 'npm test'
                    } catch (Exception e) {
                        echo "No tests available or tests failed."
                    }
                }
            }
        }
        stage('Build Application') {
            steps {
                script {
                    try {
                        sh 'npm run build'
                    } catch (Exception e) {
                        echo "No build step needed or build failed."
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo "Deploying application..."
                    
                    // Build and run the Docker container
                    sh '''
                    docker build -t my-nodejs-webapp .
                    docker run -d -p 3000:3000 --name webapp-container my-nodejs-webapp
                    '''

                    echo "Waiting for application to start..."
                    sleep(10) // Wait for the container to start

                    // Validate deployment
                    echo "Validating application in the browser..."
                    sh '''
                    curl -I http://localhost:3000 || echo "Application is not accessible. Please verify deployment."
                    '''
                }
            }
        }
    }
    post {
        always {
            echo "Cleaning up resources..."
            // Stop and remove the container
            sh '''
            docker stop webapp-container || true
            docker rm webapp-container || true
            '''
        }
    }
}
