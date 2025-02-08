pipeline {
    agent { label 'Slave'}
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

        stage("Checkout from SCM") {
            steps {
                git branch: 'master', credentialsId: 'github', url: 'https://github.com/ridodomayana/hello-world.git'
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
