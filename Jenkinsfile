pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/muthu512/DeploySpringBoot.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package -DskipTests'
            }
        }
        stage('Deploy') {
            steps {
                // Navigate to the target directory to run the JAR directly
                dir('C:\\Users\\Dell-Lap\\Downloads\\Newfolder') {
                    // Run the JAR file directly from the target folder
                    bat 'start java -jar C:\\Users\\Dell-Lap\\.jenkins\\workspace\\DeploySpringBoot\\target\\spring-boot-2-hello-world-1.0.2-SNAPSHOT.jar --server.port=1010'
                }
            }
        }
    }
}
