pipeline {
  agent any
  stages {
  stage('Install Application') { 
      steps {
        bat 'mvn clean install' 
      }
    }
    stage('Deploy CloudHub') { 
      steps {
        bat 'mvn -DmuleDeploy  -Danypoint.username=mopurutarun -Danypoint.password=Shaha@1103' 
      }
    }
  }
}