pipeline {
    agent any
    tools {
        jdk 'Java17'
        maven 'maven'
    }
    stages{
        stage("Cleanup Workspace") {
            steps {
                cleanWs()
            }
        }

        stage("Build Application") {
            steps {
                sh "mvn clean install"
            }
        }

        stage("Test Application") {
            steps {
                sh "mvn test"
            }
        }
    }
}
