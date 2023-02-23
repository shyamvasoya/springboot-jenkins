CODE_CHANGES = getGitChanges()

pipeline {
    agent any

    stages {
        stage('build') {
            when{
              expression{
                  CODE_CHANGES == true
              }
          }
            steps {
                echo 'building the application'
            }
        }
      stage('test') {
          when{
              expression{
                  env.BRANCH_NAME == 'dev'
              }
          }
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
