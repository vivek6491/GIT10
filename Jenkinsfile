pipeline {
    agent any
    stages {
        stage('Info') {
            steps {
                echo "Building branch: ${env.BRANCH_NAME}"
                echo "PR ID: ${env.CHANGE_ID}"
                echo "Source branch: ${env.CHANGE_BRANCH}"
                echo "Target branch: ${env.CHANGE_TARGET}"
            }
        }

        stage('Build1') {
            steps {
                echo "Building the project..."
                // Your actual build commands
            }
        }

        stage('Tests') {
            steps {
                echo "Running tests..."
            }
        }

        stage('Deploy (only for non-PR)') {
            when {
                expression { return env.CHANGE_ID == null }
            }
            steps {
                echo "Deploying because this is not a PR"
            }
        }
    }
}

