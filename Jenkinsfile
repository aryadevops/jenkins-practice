pipeline {
    agent { node { label 'AGENT-1' } }
    stages {
        stage('Build') {
            steps {
                echo "Build"
            }
        }
        stage('Test') {
            steps {
                echo "Test"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy"
            }
        }
    }
    post {
        always{
            echo "I will Always run"
        }
        success {
            echo "I will run only Success"
        }
        failure {
            echo "I will run only failure"
        }
    }
}