pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Clone your GitHub repository
                git url: 'https://github.com/muthu512/DeploySpringBoot.git', branch: 'master'
            }
        }

        stage('Build') {
            steps {
                // Build the project using Maven
                bat 'mvn clean package -DskipTests'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Run the JAR directly from the Newfolder
                    bat "java -jar C:\\Users\\Dell-Lap\\Downloads\\Newfolder\\spring-boot-2-hello-world-1.0.2-SNAPSHOT.jar"
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
