pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out code from Git'
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling Java program'
                bat 'javac Hello.java'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Java program'
                bat 'java Hello'
            }
        }

    }

    post {
        success {
            echo 'Build Successful!'
        }
        failure {
            echo 'Build Failed!'
        }
        always {
            archiveArtifacts artifacts: '*.class'
            echo 'Artifacts archived.'
        }
    }
}

