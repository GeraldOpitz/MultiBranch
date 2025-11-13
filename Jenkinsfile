pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building project on branch: ${env.BRANCH_NAME}"
            }
        }

        stage('Test') {
            when {
                anyOf {
                    branch 'develop'
                    branch pattern: "feature/.*", comparator: "REGEXP"
                }
            }
            steps {
                echo "Running tests for ${env.BRANCH_NAME}"
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying from ${env.BRANCH_NAME}"
            }
        }
    }

    post {
        always {
            echo "Pipeline finished for ${env.BRANCH_NAME}"
        }
    }
}
