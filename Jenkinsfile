pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository containing the app
                git 'https://github.com/your-username/ci-cd-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image with a tag
                    docker.build("ci-cd-pipeline-app")
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    // You could run tests here. For demo, let’s skip this stage.
                    echo 'Running Tests (None defined for demo)'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'docker-hub-credentials') {
                        docker.image('ci-cd-pipeline-app').push("latest")
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Example deploy step, which could be Kubernetes, Docker Compose, etc.
                    echo 'Deploying... (Define deployment steps as needed)'
                }
            }
        }
    }

    post {
        always {
            // Cleanup if needed
            echo 'Pipeline completed.'
        }
    }
}

