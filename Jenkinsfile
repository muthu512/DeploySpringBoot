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
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                // Define the destination folder on your Windows machine
                script {
                    def destinationFolder = 'C:\\Users\\Dell-Lap\\Downloads\\New folder'
                    // Copy the JAR file to the specific folder
                    bat "copy target\\*.jar ${destinationFolder}\\"
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
