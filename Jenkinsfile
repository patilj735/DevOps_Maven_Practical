pipeline {
    agent any

    tools {
        // Use the exact name you configured in Jenkins Global Tool Configuration
        jdk 'Java21'
        maven 'Maven3'   // Adjust this to match your Maven installation name
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/patilj735/DevOps_Maven_Practical.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
