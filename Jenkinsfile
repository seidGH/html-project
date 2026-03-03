pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Verify HTML File') {
            steps {
                echo 'Checking if index.html exists...'
                sh 'ls -l'
            }
        }

        stage('Archive HTML') {
            steps {
                echo 'Archiving HTML file...'
                archiveArtifacts artifacts: 'index.html', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully 🎉'
        }
        failure {
            echo 'Pipeline failed ❌'
        }
    }
}
