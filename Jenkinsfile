pipeline {
    agent any
    stages {

        stage('pull') {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Ashwinimys/Amazon-Jenkins.git'
            }
        }

        stage('compile') {
            steps {
                sh 'mvn compile'
                echo ' this is main3.0 branch'
            }
        }
stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }

    }

  post{
    
  failure{
       echo 'Failure in the build'
   }

  }

}
