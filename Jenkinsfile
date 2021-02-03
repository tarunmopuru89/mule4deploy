pipeline {
agent any
stages {
stage('Build Application') {
steps {
echo 'Application is in Building Phase'
bat 'mvn clean install'
}
}
stage('Test Application') {
steps {
echo 'Application is in Testing Phase'
bat 'mvn test'
}
}
    stage('Deploy CloudHub') { 
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypointCredentials')
      }
      steps {
        bat 'mvn clean deploy -DmuleDeploy -DskipTests -Dmule.version=4.3.0 -Danypoint.username=mopurutarun -Danypoint.password=Shaha@1103 -Denv=Sandbox -Dappname=myfirst -DvCore=Micro -Dworkers=1 -DaltDeploymentRepository=myinternalrepo::default::file:///C:/snapshots'
      }
    }
}
}