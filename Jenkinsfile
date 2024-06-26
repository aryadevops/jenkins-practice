pipeline {
    agent { node { label 'AGENT-1' } }
    options {
        ansiColor('xterm')
    }
    // Global decleration of variables,we can access any where
    // environment { 
    //     User = 'Arun'
    // }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                //echo " User name = $User"
                echo " Password = $Password"
            }
        }
        stage('Test') {
            steps {
                echo "Test"
                //echo " Test Username = $User"
                echo " Test Password = $Password"    
            }
        }
        stage('Parameters') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
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