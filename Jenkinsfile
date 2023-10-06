pipeline {
    agent any
    environment {                            // Pipeline Variables : All the stages of the pipeline can use it.
        ENV_URL = "pipeline.google.com"
    }
    stages {
        stage('Stage One') {
        environment { 
            ENV_URL = "stage.google.com"     // Stage level variable
           }
            steps {
                sh  '''
                echo Hello world
                echo Welcome to Jenkins
                echo Environment URL is ${ENV_URL}
                
                '''
            }
        }
        stage('Stage Two') {
            environment { 
            BATCH = "B55"
            }
            steps {
                sh "echo stage Two demo"
                sh "echo training batch is ${BATCH}"
            }
        }
        stage('Stage Three') {
            steps {
                sh "echo stage Three demo"
            }
        }
    }
}