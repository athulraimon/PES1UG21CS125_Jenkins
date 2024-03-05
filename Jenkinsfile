pipeline {
  agent any
  stages {
          stage('Clone repository') {
              steps {
                  checkout([$class: 'GitSCM',
                  branches: [[name: '*/main']],
                  userRemoteConfigs: [[url: 'https://github.com/athulraimon/PES1UG21CS125_Jenkins.git']]])
                
                            }
  }
 
    stage('Build') {
      steps {
        build 'PES1UG21C125'
        sh 'get main.cpp -o output'
      }
    }
    stage('Test') {
      steps {
        sh './output'
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy'
      }
    }
    post {
      failure {
        error 'Pipeline failed'
      }
    }
  }
}
  
