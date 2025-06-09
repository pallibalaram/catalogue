// #!groovy
// @Library('roboshop-shared-library') _

// def configMap = [
//     application: "nodejsVM",
//     component: "catalogue"
// ]
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
    //    nexusUrl = '172.31.81.30:8081'         
    }
    parameters {
    //     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

           booleanParam(name: 'Deploy', defaultValue: false, description: 'Toggle this value')

    //     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('get the version') {
            steps {
                script {
                    def packageJson = readJSON file: 'package.json'
                    packageVersion = packageJson.version
                    echo "application version: $packageVersion"
                }
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