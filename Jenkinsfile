

pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3'
    }
    
    stages {
        stage('build') {
            
            steps {
                echo 'building the application'
                echo "Software version is ${NEW_VERSION}"
            }
        }
      stage('test') {
          //when{  
          //    expression{
          //        env.BRANCH_NAME == 'dev'
          //    }
          //}
            steps {
                echo 'testing the application'
            }
        }
      stage('deploy') {
            steps {
                echo 'deploying the application'
                // sh 'wrong command'
                //echo "${SERVER_CREDENTIALS}"
            //     withCredentials([
            //         usernamePassword(credentials: 'docker', usernameVariable : USER, passwordVariable : PWD)
            //     ]){
            //         //echo "user is ${USERNAME}"
            //     }
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
