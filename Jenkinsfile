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
                    // Set the deployment folder where the JAR is to be built
                    def deployFolder = "C:\\Users\\Dell-Lap\\Downloads\\Newfolder"
                    def jarFile = "${deployFolder}\\target\\spring-boot-2-hello-world-1.0.2-SNAPSHOT.jar"
                    
                    // Run the JAR directly from the deployment folder
                    bat "java -jar ${jarFile}"
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
