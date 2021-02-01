pipeline {
agent any
stages {
stage(‘Build’) {
steps {
bat ‘mvn clean install’
}
}
stage(‘Test’) {
steps {
bat ‘mvn test’
}
}
stage(‘Deploy CloudHub’) {
environment {
ANYPOINT_CREDENTIALS = credentials(‘anypointPlatform’)
}
steps {
bat ‘mvn package deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2’
}
}
}
}