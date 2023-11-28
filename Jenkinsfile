pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Define build steps here
                sh 'make build'
            }
        }
        stage('Test') {
            steps {
                // Define test steps here
                sh 'make test'
            }
        }
        stage('Deploy') {
            when {
                branch 'master'
            }
            steps {
                // Define deployment steps here
                sh 'make deploy'
            }
        }
    }
    post {
        success {
            // Actions to perform on pipeline success
            mail to: 'team@example.com', subject: 'Pipeline Succeeded', body: 'The pipeline completed successfully.'
        }
        failure {
            // Actions to perform on pipeline failure
            mail to: 'dev@example.com', subject: 'Pipeline Failed', body: 'The pipeline failed, please check logs.'
        }
    }
}
