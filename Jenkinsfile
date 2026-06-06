
//SCRIPTED
// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo "Integration Test"
// 	}
// }


//DECLARATIVE

pipeline{
	agent any
	//agent {docker {image 'maven:3.6.3'}}
	environemt{
		dockerHome = tool "myDocker"
		mavenHome = tool "myManven"
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh "mvn --version"
				sh "docker version"
				echo "Build"
			}
		}
		stage('Test'){
			steps{
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"
			}
		}
	}
	post{
		always{
			echo "I am run always"
		}
		success{
			echo "I run when you are successfull"
		}
		failure{
			echo "I run when you are fail"
		}
	}
}