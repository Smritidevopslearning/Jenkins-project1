pipeline {
    agent none
    tools {
        maven 'maven3'
    }

    stages {
        stage('Checkout') {
            agent {
                 label 'master' 
                }
            steps{
              git url: 'https://github.com/Smritidevopslearning/Jenkins-project1.git', branch: 'main'
            }
        }

        stage('Build') {
            agent {
                 label 'slave1'
                  }
            steps {
              echo "Build stage is in progress"
              sh 'mvn clean compile'
            }
        }

        stage('Test') {
            agent {
                 label 'slave2'
                  }
            steps {
                echo "Test is in progress"
                sh 'mvn test'
            }
        }
    }
}
