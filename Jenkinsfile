pipeline {
    agent any
    environment {
        VERSION = '1.0.0'
        BUILD_NUMBER = "${env.BUILD_ID}"
    }
    stages {
        stage('Build') {
            steps {
                echo "Building version: ${VERSION}"
                echo "Build number: ${BUILD_NUMBER}"
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo "Testing version: ${VERSION}"
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying version: ${VERSION}"
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            echo 'Pipeline Completed'
        }
    }
}
