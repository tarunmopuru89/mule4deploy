pipeline {
  agent any
  stages {
    stage('Deploy CloudHub') { 
      steps {
        bat 'mvn deploy -DmuleDeploy  -Danypoint.username=mopurutarun -Danypoint.password=Shaha@1103' 
      }
    }
  }
}