pipeline {
    agent { node { label 'AGENT-1' } }
    options {
        ansiColor('xterm')
    }
    // Global decleration of variables,we can access any where
    environment { 
        User = 'Arun'
    }
    stages {
        stage('Build') {
            environment { 
                Password = 'Arun@123'
            }
            steps {
                sh '''
                    ls -ltr
                    pwd
                '''
                echo "Build"
                echo "this is from webhook trigger"
                echo " User name = $User"
                echo " Password = $Password"
            }
        }
        stage('Test') {
            steps {
                echo "Test"
                echo " Test Username = $User"
                echo " Test Password = $Password"    
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