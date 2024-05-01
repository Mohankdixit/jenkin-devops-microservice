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
	//agent { docker { image 'maven:3.6.3'} }
	environment{
		dockerHome = tool "myDocker"
		MavenHome = tool "myMaven"
		path = "$dockerHome/bin:$MavenHome/bin:$path"
	}
	stages{
		stage('Checkout'){
			steps{
				sh "mvn --version"
				sh "docker version"
				echo 'Build'
				echo "path - $path"
				echo "build_number - $env.build_number"
				echo "build-tag - $env.build_tag"
				echo "job_name - $env.job_name" 
			}
		}
		stage('Compile'){
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps{
				//echo 'Test'
				sh "mvn test"
			}
		}
		stage('Integration Testing'){
			steps{
				//echo 'Integration testing'
				sh "mvn failsafe:integration-test failsafe:verify"
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
