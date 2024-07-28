pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Example build step, adjust according to your project
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                // Example test step, adjust according to your project
                sh './gradlew test'
            }
        }
    }
    post {
        always {
            // Actions to take after completion, like archiving artifacts or sending notifications
            archiveArtifacts artifacts: '*/build/libs/.jar', allowEmptyArchive: true
            junit 'build/test-results/test/*.xml'
        }
    }
}
