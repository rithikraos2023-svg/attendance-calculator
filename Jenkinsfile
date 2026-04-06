pipeline {
    agent any

    tools {
        maven 'M3' // Make sure 'Maven' matches the name configured in Jenkins Global Tools
    }

    stages {
        stage('Checkout Code') {
            steps {
                // This pulls your latest code from GitHub
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                echo 'Running Maven to build and test the Attendance Calculator...'
                // Runs the Maven command on Windows
                bat 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Awesome! The Pipeline executed successfully!'
        }
        failure {
            echo 'Oh no! The Pipeline failed. Check the Jenkins console logs.'
        }
    }
}