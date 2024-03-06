pipeline{
  agent any
  stages {
          stage('Clone repository'){
            steps {
              checkout([$class: 'GitSCM',
              branches: [[name: '*/main']],
              userRemoteConfigs: [[url: '']]])
            }
          }
    stage('Build'){
        steps {
          build 'PES2UG21CS291-1'
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
  
  
