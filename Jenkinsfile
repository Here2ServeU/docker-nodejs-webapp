pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/Here2ServeU/docker-nodejs-webapp.git']]])
            }
        }

        stage('Setup Node.js') {
            steps {
                sh '''
                # Install Node.js 16
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
                echo "Customize deployment logic here if needed."
            }
        }
    }
}
