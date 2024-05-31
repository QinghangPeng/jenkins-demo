pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "jenkins-demo-image"
    }

    stages {
        stage("Build with Gradle") {
            steps {
                script {
                    echo "Building the project with Gradle..."
                    sh "./gradlew clean build"
                }
            }
        }

        stage("Build Docker Image") {
            steps {
                script {
                    echo "Building Docker image..."
                    sh "docker build -t ${DOCKER_IMAGE} ."
                }
            }
        }

        stage("Run Docker Container") {
            steps {
                script {
                    echo "Running Docker container..."
                    sh "docker stop ${DOCKER_IMAGE} || true && docker rm ${DOCKER_IMAGE} || true"
                    sh "docker run -d --name ${DOCKER_IMAGE} -p 8081:8081 ${DOCKER_IMAGE}"
                }
            }
        }
    }

    post {
        always {
            echo "Cleaning up..."
            deleteDir()
        }
        success {
            echo "Build and deployment success"
        }
        failure {
            echo "Build or deployment failed"
        }
    }
}
