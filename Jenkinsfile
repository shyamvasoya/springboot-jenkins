pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                echo 'building the application'
            }
        }
      stage('test') {
            steps {
                echo 'testing the application'
            }
        }
      stage('deploy') {
            steps {
                echo 'deplying the application'
                sh 'wrong command'
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
