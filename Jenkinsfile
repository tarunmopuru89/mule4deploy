pipeline {
  agent any
  stages {
    stage('Unit Test') { 
      steps {
        sh 'mvn clean test'
      }
    }
    stage('Deploy CloudHub') { 
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
      steps {
        sh 'mvn deploy -P cloudhub  -Danypoint.username=mopurutarun -Danypoint.password=Shaha@1103 -Denvironment=DeployTest' 
      }
    }
  }
}