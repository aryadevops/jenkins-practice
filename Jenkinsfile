pipeline {
    agent { node { label 'AGENT-1' } }
    options {
        ansiColor('xterm')
    }
    stages {
        stage('Build') {
            steps {
                sh '''
                    ls -ltr
                    pwd
                '''
                echo "Build"
                echo "this is from webhook trigger"
            }
        }
        stage('Test') {
            steps {
                echo "Test"
            }
        }
        stage(Approve){
            steps{
                input "Shell I Apply"
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