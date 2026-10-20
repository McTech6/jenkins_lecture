
pipeline {
    agent any

    environment {
        RECIPIENT_EMAIL = 'your-real-email@gmail.com'
    }

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
                to: "${RECIPIENT_EMAIL}",
                subject: "SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Hello,

Your Jenkins pipeline completed successfully.

Job: ${env.JOB_NAME}
Build Number: ${env.BUILD_NUMBER}
Status: ${currentBuild.currentResult}
Build URL: ${env.BUILD_URL}

Regards,
Jenkins
"""
            )
        }

        failure {
            emailext(
                to: "${RECIPIENT_EMAIL}",
                subject: "FAILED: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Hello,

Your Jenkins pipeline has failed.

Job: ${env.JOB_NAME}
Build Number: ${env.BUILD_NUMBER}
Status: ${currentBuild.currentResult}
Build URL: ${env.BUILD_URL}

Please check the Jenkins console output to investigate the failure.

Regards,
Jenkins
"""
            )
        }

        always {
            echo "Pipeline execution finished with status: ${currentBuild.currentResult}"
        }
    }
}
