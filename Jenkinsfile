pipeline {
    agent any

    environment {
        GITHUB_SSH_CREDENTIALS = 'GitHub SSH Key'  // Replace with your SSH credentials ID
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Use SSH URL and credentials for GitHub authentication
                    checkout scm: [
                        $class: 'GitSCM',
                        branches: [[name: 'refs/heads/main']],
                        userRemoteConfigs: [[
                            url: 'git@github.com:niks1212/CI-CD-Pipeline.git',
                            credentialsId: GITHUB_SSH_CREDENTIALS
                        ]]
                    ]
                }
            }
        }

        // Other stages here (Build, Deploy, etc.)
    }
}
