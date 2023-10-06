pipeline {
    agent any
    environment {
        ENV_URL = "pipeline.google.com"
    }
    stages {
        stage('Stage One') {
            steps {
                sh  '''
                echo Hello world
                echo Welcome to Jenkins
                echo Environment URL is ${ENV_URL}
                
                '''
            }
        }
        stage('Stage Two') {
            steps {
                sh "echo stage Two demo"
            }
        }
        stage('Stage Three') {
            steps {
                sh "echo stage Three demo"
            }
        }
    }
}