pipeline {
    agent any // This defines the agent (node) Jenkins will run the pipeline on.

    stages {
        // Stage 1: Checkout code from GitHub
        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
                checkout scm
            }
        }

        // Stage 2: Build the application
        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'build.bat' // Replace with your actual build script or command for Windows.
            }
        }

        // Stage 3: Run unit tests
        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'test.bat' // Replace with your actual test script or command for Windows.
            }
        }

        // Stage 4: Deploy the application
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                bat 'deploy.bat' // Replace with your actual deployment script or command for Windows.
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            cleanWs() // Clean the workspace after the pipeline completes
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs for details.'
        }
    }
}
