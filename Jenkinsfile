pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage('Build Maven') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t maven-app .'
            }
        }

        stage('Run Docker') {
            steps {
                bat 'docker run --rm maven-app'
            }
        }
    }
}