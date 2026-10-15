pipeline {
    agent any

    parameters {
        string(name: 'IMAGE_TAG', defaultValue: 'latest', description: 'Docker image tag')
        booleanParam(name: 'PUSH_IMAGE', defaultValue: true, description: 'Push image to Docker Hub?')
    }

    environment {
        IMAGE_NAME = "devopssteps/my-app-15"
    }

    stages {
        stage('clone') {
            steps {
                echo 'clone code............'
                checkout scm
            }
        }

        stage('build image') {
            steps {
                echo "Building Docker image with tag: ${params.IMAGE_TAG}"
                echo "Pretend command: docker build -t ${IMAGE_NAME}:${params.IMAGE_TAG} ."
            }
        }

        stage('push image') {
            when {
                expression { return params.PUSH_IMAGE }
            }
            steps {
                echo "Pretend command: docker push ${IMAGE_NAME}:${params.IMAGE_TAG}"
            }
        }
    }
}
