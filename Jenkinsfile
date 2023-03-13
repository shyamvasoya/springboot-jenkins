pipeline {
    agent any
    //tools{
        //maven 'maven-3.9.0'
    //}

    stages {
        stage('build') {
            steps {
                echo 'Building the application'
                sh 'mvn package'
                //sh 'wrong command'
            }
        }
        stage('test') {
            steps {
                echo 'Testing the application'
            }
        }
        stage('deploy') {
            steps {
                echo 'Depoying the application'
            }
        }
    }
    post {
        success{
            echo 'This is going to be executed when pipeline will be executed successfully'
        }
        failure{
            echo 'Whenever something goes wrong'
        }
        always{
            echo 'This will be executed always'
        }
    }
}
