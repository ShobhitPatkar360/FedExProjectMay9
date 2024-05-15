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
				echo "Archieving the Artifacts"
				archiveArtifacts artifacts: '**/*.war', followSymlinks: false
				echo "Check your archieved atifacts"
				
			}
		}
		stage("Deploy on Prod Server"){
			steps{
				echo "Deploying on Prod Server"
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
