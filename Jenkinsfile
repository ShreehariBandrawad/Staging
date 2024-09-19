pipeline {
    parameters {
        choice(name: 'terraformAction', choices: ['apply', 'destroy'], description: 'Choose the Terraform action to perform')
    } 
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-repo/sample-java-app.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    // Assuming you're using Maven
                    sh 'mvn clean install'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Run tests using Maven
                    sh 'mvn test'
                }
            }
        }
        stage('Package') {
            steps {
                script {
                    // Package the application
                    sh 'mvn package'
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add your deployment script or commands here
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
