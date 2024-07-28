pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Build the project
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                // Run the tests
                sh './gradlew test'
            }
        }
    }
    post {
        always {
            // Actions to take after the pipeline completes
            archiveArtifacts artifacts: '*/build/libs/.jar', allowEmptyArchive: true
            junit 'build/test-results/test/*.xml'
        }
    }
}
