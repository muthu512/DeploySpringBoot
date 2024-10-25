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
                    // Set the path to the JAR file
                    def jarFile = "C:\\Users\\Dell-Lap\\Downloads\\spring-boot-hello-world-main\\spring-boot-hello-world-main\\target\\spring-boot-2-hello-world-1.0.2-SNAPSHOT.jar"

                    // Run the JAR directly from the target folder with specified port
                    bat "java -jar ${jarFile} --server.port=1010"
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
