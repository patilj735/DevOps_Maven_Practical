pipeline {
    agent any

    tools {
        maven 'Maven'   // Must match Jenkins Global Tool Configuration
        jdk 'JDK'       // Configure this as JDK 21 in Jenkins
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'mvn clean compile'
                    } else {
                        bat 'mvn clean compile'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'mvn test'
                    } else {
                        bat 'mvn test'
                    }
                }
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
    }
}

// pipeline {
//     agent any

//     stages {
//         stage('Checkout') {
//             steps {
//                 checkout scm
//             }
//         }
//         stage('Build') {
//             steps {
//                 // This runs the Maven command using the pom.xml
//                 bat 'mvn clean compile'
//             }
//         }
//         stage('Test') {
//             steps {
//                 bat 'mvn test'
//             }
//         }
//     }
// }
