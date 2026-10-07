pipeline {
    agent any
    environment{
        name = 'pranav'
    }
    parameters {
        string(name: 'person', defaultValue: 'Pranav Bavcha', description: "who are you?")
        booleanParam(name: 'isMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Jaipur','Mumbai','Pune'], description: "")
    }
    stages {
        stage('Run A command') {
            steps {
                sh '''
                ls
                date
                pwd
                cal 2021
                '''
            }
        }
        stage('Environment Variables') {
            environment{
                username = 'myusername'
                
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
                
            }
        }
        stage('Parameters') {
            steps {
                echo 'deploy no test'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        stage('Continue ?') {
            input {
                message "Should we continue?"
                ok "Yes we Should"
            }
            steps {
                echo 'Deploy on prod'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Deploy on prod'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure {
            echo 'Failure'
        } 
    success {
        echo 'Success'
        
    }
        
    }
    
}
