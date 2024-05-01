// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo "Test"
// 	}
// }

pipeline{
	//agent any
	agent { docker { image 'maven:3.6.3'} }
	stages{
		stage('Build'){
			steps{
				sh "mvn --version"
				echo 'Build'
			}
		}
		stage('Test'){
			steps{
				echo 'Test'
			}
		}
		stage('Integration Testing'){
			steps{
				echo 'Integration testing'
			}
		}
	}
	post{
		always{
			echo 'i am successfull'
		}
		failure{
			echo 'i am failed'
		}
		success{
			echo 'i got success'
		}
	}
}
