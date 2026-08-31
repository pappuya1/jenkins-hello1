pipeline {
    agent any

    triggers {
        pollSCM('H/2 * * * *')   // poll every ~2 minutes
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Say hello') {
            steps {
                echo 'Hello from my first Jenkins pipeline!'
                sh 'echo "Built at: $(date)"'
                sh 'echo "Commit: $(git rev-parse --short HEAD)"'
            }
        }
    }

    post {
        always { echo 'Pipeline finished.' }
    }
}
