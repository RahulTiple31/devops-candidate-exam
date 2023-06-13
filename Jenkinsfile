pipeline {
    agent any
    environment {
        name = 'guddu'
    }
    parameters{
        string(name : 'person', defaultValue: 'Guddu Tiple', description: "Who are you...?")
        booleanParam(name : 'is Male', defaultValue: true, description: "")
        choice(name : 'City', choices: ['Nagpur', 'Pune', 'Mumbai'], description: "")
    }
        stages {
        stage (Dev) {
            steps {
                echo 'Dev Task completed'
                sh 'sleep 10s'
                sh 'date'
                sh 'netstat -tunlp'
            }
        }
        
        stage ('Continue ?') {
            input {
                message "Should we continue ?"
                ok "Yes we should"
                
            }
            steps {
                sh 'echo User name is "$name"'
            }
        }
          
        
        stage (QA) {
            steps {
                echo 'QA Task completed'
                sh '''
                pwd
                cal
                '''
            }
        }
        
        stage ('Parameters') {
            steps {
                sh 'echo User name is "$name"'
                sh 'echo User full name is "$person"'
            }
        }
        
        stage (Prod) {
            steps {
                echo 'Prod Task completed'
                sh 'ls -l'
            }
        }
        
        stage (Pipeline) {
            environment {
                UserName = 'Guddu Tiple'
            }
            steps {
                echo 'Jenkins pipeline successed'
                sh 'echo User full name is "$UserName"'
            }
        }
        
         stage ('Enviroment varible') {
            steps {
                sh 'echo Build task-"$BUILD_ID"'
                sh 'echo User name is "$name"'
                sh 'echo User full name is "$UserName"'
            }
        }
    }
    post {
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'Failur'
        }
        success { 
            echo 'Success'
        }
    }
}
