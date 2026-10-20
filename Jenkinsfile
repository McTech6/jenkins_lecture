
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'exit 0'
            }
        }
    }

    post {
        success {
            emailext(
                subject: "Build SUCCESS: ${env.JOB_NAME}",
                body: "Job ${env.JOB_NAME} build #${env.BUILD_NUMBER} was successful.",
                to: 'recipient@example.com'
            )
        }

        failure {
            emailext(
                subject: "Build FAILURE: ${env.JOB_NAME}",
                body: "Job ${env.JOB_NAME} build #${env.BUILD_NUMBER} failed.",
                to: 'recipient@example.com'
            )
        }

        always {
            echo 'Pipeline execution finished.'
        }
    }
}
