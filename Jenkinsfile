pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    options {
        timeout(time: 1, unit: 'HOURS') 
        disableConcurrentBuilds()
    }
    environment {
       packageVersion = ''         
    }
    // parameters {
    //     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

    //     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

    //     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    // }
    stages {
        stage('get the version') {
            steps {
                script {
                    def packageJson = readJSON file: 'package.json'
                    packageVersion = pacakageJason.version
                    echo "application version is :$pacakageVersion"
                }
            }
        }
        stage('install dependencies') {
            steps {
                sh """ 
                    npm install
                """ 
            }
        }
        stage('Build') {
            steps {
                echo 'this block is for Building'
            }
        }
        stage('Test') {
            steps {
                echo 'this block is for Testing'
            }
        }
        stage('Deploy') {
            steps {
                echo 'this block is for Deploying....'
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
        success {
            echo "pipeline is success"
        }
        failure {
            echo "pipeline is failed"
        }    
    }
}