pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'Maven' // Assumes Maven is configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone the repository
                git 'https://github.com/your-repo/my-java-app.git'
            }
        }
        stage('Build') {
            steps {
                // Run Maven build
                sh "${MAVEN_HOME}/bin/mvn clean package"
            }
        }
        stage('Test') {
            steps {
                // Run tests
                sh "${MAVEN_HOME}/bin/mvn test"
            }
        }
        stage('Deploy') {
            steps {
                // Deploy the application (placeholder)
                sh 'echo Deploying the application...'
            }
        }
    }
    post {
        always {
            // Archive artifacts, test results, etc.
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
            junit 'target/surefire-reports/*.xml'
        }
    }
}
