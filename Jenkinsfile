
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: Pipeline completed successfully!'
        }

        failure {
            echo 'FAILURE: Pipeline failed!'
        }

        always {
            echo 'ALWAYS: Pipeline execution has finished.'
        }

        unstable {
            echo 'UNSTABLE: Pipeline completed with warnings or unstable tests.'
        }

        changed {
            echo 'CHANGED: Pipeline status differs from the previous run.'
        }

        fixed {
            echo 'FIXED: Pipeline is successful after a previous failure or unstable run.'
        }

        aborted {
            echo 'ABORTED: Pipeline was manually or externally aborted.'
        }

        cleanup {
            echo 'CLEANUP: Performing final cleanup tasks.'
        }
    }
}
