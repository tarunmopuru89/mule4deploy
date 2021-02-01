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
        bat 'mvn deploy -Danypoint.username=mopurutarun -Danypoint.password=Shaha@1103 -DaltDeploymentRepository=cloudhub::default::https://maven.anypoint.mulesoft.com/api/v2/organizations/97c78d17-bb48-4f76-abb4-e95374cf3578/maven' 
      }
    }
  }
}