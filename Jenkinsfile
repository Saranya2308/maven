pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your Git repository
                git url: 'https://github.com/Saranya2308/maven.git', branch: 'main' 
            }
        }

        stage('Build') {
            steps {
                // Build the project using Maven and skip tests
                bat './mvnw clean package -DskipTests'
            }
        }

        stage('Test') {
            steps {
                // Run tests (optional, you can remove or comment this if not required)
                bat './mvnw test'
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy to your target environment (Optional, modify this step based on your setup)
                // Example: sh './deploy.sh' or any other deployment logic you use.
                echo 'Deployment stage (modify this step as per your needs)'
            }
        }
    }

    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
        always {
            echo 'Pipeline completed!'
        }
    }
}
