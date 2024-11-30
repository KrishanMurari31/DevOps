pipeline {
    agent any // This defines that the pipeline can run on any available agent.

    stages {
        // Stage 1: Checkout code from GitHub
        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
                checkout scm
            }
        }

        // Stage 2: Display files
        stage('List Files') {
            steps {
                echo 'Listing the files in the repository...'
                bat 'dir' // Use 'ls' for Linux instead of 'dir'
            }
        }

        // Stage 3: Execute code (example using 'code' file)
        stage('Execute Code') {
            steps {
                echo 'Running the "code" file...'
                bat 'type code' // Replace 'type code' with the correct command based on file content
            }
        }

        // Stage 4: Process Python script (if any)
        stage('Run Python Script') {
            when {
                expression {
                    fileExists('python') // Ensure the 'python' file exists
                }
            }
            steps {
                echo 'Running the Python script...'
                bat 'python python' // Ensure Python is installed on the agent
            }
        }

        // Stage 5: Placeholder for other files
        stage('Process Other Files') {
            steps {
                echo 'Processing other files (e.g., FIRE, ICE, WATER)...'
                bat 'type FIRE' // Example of reading a file
                bat 'type ICE'
                bat 'type WATER'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace...'
            cleanWs() // Cleans up the workspace after execution
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs for details.'
        }
    }
}
