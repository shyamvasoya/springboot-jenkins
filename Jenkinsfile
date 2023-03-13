pipeline {
    agent any
    tools{
        maven 'maven-3.9.0'
    }

    stages {
        stage('build') {
            steps {
                echo 'Building the application with web hook'
                sh 'mvn package'
                //sh 'wrong command'
            }
        }
        stage('test') {
            steps {
                echo 'Testing the application'
                sh 'mvn test'
            }
        }
        stage('deploy') {
            steps {
                echo 'Depoying the application'
                withCredentials([usernamePassword(credentialsId: 'docker', usernameVariable : 'USERNAME', passwordVariable : 'PASSWORD')]){
                    sh 'docker build -t learnwithparth/spring-boot:2.1 .'
                    sh "docker login -u $USERNAME -p $PASSWORD"
                    sh 'docker push learnwithparth/spring-boot:2.1'
                }
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
