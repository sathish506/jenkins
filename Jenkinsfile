pipeline {
    agent any
    environment {                            // Pipeline Variables : All the stages of the pipeline can use it.
        ENV_URL = "pipeline.google.com"
        SSH_CRED = credentials('SSH_CRED')  
    }
       triggers { 
        pollSCM('*/59 * * * 1-5') 
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?') 
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

     tools {
        maven 'maven-3.9.4' 
    }

    stages {
        stage('Stage One') {
        environment {                                     // Stage level variable
            ENV_URL = "stage.google.com"                           
              }
            steps {
                sh  '''
                echo Hello world
                echo Welcome to Jenkins
                echo Environment URL is ${ENV_URL}
                mvn -v

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