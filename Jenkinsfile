pipeline{
  agent any
  stages {
          stage('Clone repository'){
            steps {
              checkout([$class: 'GitSCM',
              branches: [[name: '*/main']],
              userRemoteConfigs: [[url: 'https://github.com/Sp080six/PES2UG21CS536_Jenkins.git']]])
            }
          }
    stage('Build'){
        steps {
          build 'PES2UG21CS536-1'
          sh 'g++ sample.cpp -o output'
        }
    }
    stage('Deploy') {
        steps {
            echo 'deploy'
        }
    }
}
post{
  failure{
    error 'Pipeline failed'
  }
}
}
