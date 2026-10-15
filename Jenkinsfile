pipeline {
    agent any
    environment {
        IMAGE_NAME = "devopssteps/my-app"
    }

    stages {
        stage('build') {
            steps {
                echo "${IMAGE_NAME}"
            }
        }
         stage('deploy') {
            steps {
                echo 'Hello Deploy'
            }
        }
    }
}
