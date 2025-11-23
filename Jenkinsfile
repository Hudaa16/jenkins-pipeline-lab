pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    environment {
        VERSION = '1.0.0'
        BUILD_NUMBER = "${env.BUILD_ID}"
    }
    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Execute test stage?')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building version: ${VERSION}"
                echo "Build number: ${BUILD_NUMBER}"
                echo 'Building..'
                bat 'mvn -version'
            }
        }
        stage('Test') {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo "Testing version: ${VERSION}"
                echo 'Testing with conditions..'
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
