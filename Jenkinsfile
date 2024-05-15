pipeline {
	agent any
	stages{
		stage("Test"){
			steps{
				echo "Executing Test Stage"
			}
		}
		stage("Build"){
			steps{
				echo "Executing Build Stage"
			}
		}
		stage("Deploy on Test Server"){
			steps{
				echo "Deploying on Test Server"
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
