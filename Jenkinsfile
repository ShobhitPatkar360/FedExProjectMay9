pipeline {
	agent any
	tools{
		maven "maven-3.9.6"
	}
	stages{
		stage("Test"){
			steps{
				echo "Performing testing"
				sh "mvn test"
			}
		}
		stage("Build"){
			steps{
				echo "Performing Building"
				sh "mvn package"
			}
		}
		stage("Deploy on Test Server"){
			steps{
				echo "Deploying to tomcat server"
				deploy adapters: [tomcat9(credentialsId: 'tomcat-credentials', path: '', url: 'http://100.27.214.59:8080')], contextPath: 'app', war: '**/*.war'
				echo "go to webpage http://100.27.214.59:8080/app to see your webpage"
				
			}
		}
		stage("Deploy on Prod Server"){
			steps{
				echo "Deploying on Prod Server"
				deploy adapters: [tomcat9(credentialsId: 'tomcat-credentials', path: '', url: 'http://3.93.170.228:8080')], contextPath: 'product-app', war: '**/*.war'
				echo "go to webpage prod-app http://3.93.170.228:8080/product-app to see your webpage"
				
			}
		}
	}
	post{
		always{
			echo "Always Post Block"
		}
		success{
			echo "Pipeline Executed Successfully"
		}
		failure{
			echo "Pipeline Execution Failed"
		}
	}
}
