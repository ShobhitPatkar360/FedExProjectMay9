pipeline {
	agent any
	stages{
		stage("Test"){
			echo "Executing Test Stage"
		}
		stage("Build"){
			echo "Executing Build Stage"
		}
		stage("Deploy on Test Server"){
			echo "Deploying on Test Server"
		}
		stage("Deploy on Prod Server"){
			echo "Deploying on Prod Server"
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
