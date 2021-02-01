pipeline{
 agent any
 stages {
 	stage ('Build'){
 		steps {
 			withMaven(maven:'maven'){
 				sh 'mvn -f mule-jenkins-pipeline/pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven:'maven'){
 				sh 'mvn -f mule-jenkins-pipeline/pom.xml package deploy  -Dusername=mopurutarun -Dpassword=Shaha@1103 -Denvironment=DeployTest -DmuleDeploy'
 			}
 		}
 	}
 }
}