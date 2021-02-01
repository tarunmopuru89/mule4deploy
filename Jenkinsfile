pipeline {
  agent any
  stages {
    stage('Deploy') { 
      steps {
        sh 'mvn deploy -P cloudhub  -Danypoint.username=mopurutarun -Danypoint.password=Shaha@1103 -Denvironment=DeployTest' 
      }
    }
  }
}