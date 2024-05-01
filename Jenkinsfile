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
	agent any
	stages{
		stage('Build'){
			steps{
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
			echos 'i got success'
		}
	}
}
