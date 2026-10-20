pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                bat 'mvn -f java-cicd/pom.xml clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn -f java-cicd/pom.xml test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn -f java-cicd/pom.xml package'
            }
        }
    }

    post {
        success {
            echo 'Java CI pipeline completed successfully!'
        }
        failure {
            echo 'Java CI pipeline failed. Check the console output.'
        }
    }
}