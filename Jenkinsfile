pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo "Checked out branch: ${env.BRANCH_NAME}"
            }
        }
        stage('Compile') {
            steps {
                // compile Hello.java
                sh 'javac Hello.java'
            }
        }
        stage('Run') {
            steps {
                sh 'java Hello'
            }
        }
        stage('Archive') {
            steps {
                // archive the Hello.java and console log
                archiveArtifacts artifacts: 'Hello.java', fingerprint: true
            }
        }
    }
    post {
        always {
            echo "Build finished for ${env.BRANCH_NAME}"
        }
    }
}
