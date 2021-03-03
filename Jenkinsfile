import org.jenkinsci.plugins.cloudhubdeployer.common.*;
import org.jenkinsci.plugins.cloudhubdeployer.data.*;
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
   stage('Deploy to CloudHub') {
            steps {
                cloudhubDeployer(environmentId :'cd263dac-26db-4bb4-b55f-4c25f9ceac27', 
				orgId :'60c598cf-f541-4afe-a50c-9aa707f80f37',
				requestMode : RequestMode.CREATE_OR_UPDATE, 
				appName :'mules4deploy',
				credentialsId :'anypointCredentials', 
				muleVersion :'4.3.0',
				region :'us-east-1', 
				filePath :'target/*.jar',
				timeoutConnection : 90000,
				timeoutResponse : 90000,
				debugMode : DebugMode.DISABLED,
				ignoreGlobalSettings : true,
				autoStart : true,
				workerAmount : 1,
				workerType : 'Small',
				workerWeight : '0.2',
				workerCpu : '0.2',
				workerMemory : '1 GB',
				monitoringEnabled : true,
				monitoringAutoRestart : true,
				loggingNgEnabled : true,
				persistentQueues : false,
				persistentQueuesEncrypted : false,
				objectStoreV1 : false,
				envVars : [envVars(key : 'env' , value :  'DeployTest')],
				logLevels : [logLevels(levelCategory : LogLevelCategory.DEBUG ,
				packageName : 'some.package.name')],
				verifyDeployments : true)
            }
        }
    }
}
