pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3'
    }

    parameters {
        choice(name: 'VERSION', choices:['1','2','3'], description: '')
        booleanParam(name: 'executeTest', defaultValue : true, description: '')
    }
    
    stages {
        stage('init'){
            steps{
                script{
                    gv = load "script.groovy"
                }
            }
        }
        stage('config'){
            steps{
                script{
                    gv.config()
                }
            }
        }
        stage('build') {
            
            steps {
                echo 'building the application'
                echo "Software version is ${NEW_VERSION}"
            }
        }
      stage('test') {
          when{  
             expression{
                 params.executeTest
             }
          }
            steps {
                echo 'testing the application'
            }
        }
      stage('deploy') {
        input{
            message "Select the environment to deploy"
            ok "done"
            parameters{
                choice(name: 'Type', choices:['Dev','Test','Deploy'], description: '')
            }
        }
            steps {
                echo 'deploying the application'
                // sh 'wrong command'
                //echo "${SERVER_CREDENTIALS}"
                withCredentials([usernamePassword(credentialsId: 'docker', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]){
                    echo "user is ${USERNAME}"
                    echo "Type is ${Type}"
                }
             }
        }
    }
    post{
        always{
            echo 'Executing always'
        }
        success{
            echo 'Executing success'
        }
        failure{
            echo 'Executing failure'
        }
    }
}
