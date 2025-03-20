pipeline {
    agent any  // Runs on any available Jenkins node

    tools {
        maven 'Maven-3.8.6'  // Use the configured Maven installation
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/amodh-2002/spring-petclinic.git'  // Replace with your repository
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Clean old artifacts and build the project
            }
        }

        stage('Run Tests') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }
    }

    post {
        success {
            echo 'Build and tests passed successfully!'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}
