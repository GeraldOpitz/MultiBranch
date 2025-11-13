pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo "Hello from ${env.BRANCH_NAME}!"
            }
        }
    }
    post {
        always {
            echo "This always runs"
        }
    }
}
