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
        bat 'mvn package deploy -DmuleDeploy -DmuleVersion=4.3.0 -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2'
      }
    }
}
}