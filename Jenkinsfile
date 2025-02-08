pipeline {
    agent any
    tools {
        jdk 'Jdk17'
        maven 'maven'
    }
    environment {
        APP_NAME = "hello-world"
    }
    
    stages{
        stage("Cleanup Workspace") {
            steps {
                cleanWs()
            }
        }

        stage("Build Application") {
            steps {
                sh "mvn clean package"
            }
        }

        stage("Test Application") {
            steps {
                sh "mvn test"
            }
        }
    }
}
