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
        bat 'mvn deploy -P cloudhub -Danypoint.username=mopurutarun -Danypoint.password=Shaha@1103' 
      }
    }
  }
}