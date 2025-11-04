pipeline {
	agent { 
		label 'Jenkins-Agent'
		 }
	tools {
		jdk 'Java17'
		maven 'Maven'
	}
	stages{ 
		stages("Cleaning Workspace") {
		 	steps {
			cleanWs()
		    }
	    }
		stages("Checkout from SCM"){
			steps{
				git branch: 'main', credentialsId: 'github' , url: 'https://https://github.com/raoneface/register-app'
			}
		}
		stages("Build Application"){
			steps {
				sh "mvn clean package"
			}
		}
		steps("Test Application"){
			steps {
				sh "mvn test"
			}
		}
    }
}
