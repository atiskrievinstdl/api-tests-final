pipeline {
	agent any
	triggers{
		pollSCM('*/1 * * * *')
	}
	stages {
		stage('prepareDocker') {
			steps{
				script{
					prepare()
				}
			}
		}
	}
}

def prepare(){
	echo "Building api-tests-final..."
	sh "docker build -t atiskrievinstdl/api-tests-final:latest ."

	echo "Pushing the image to Docker registry"
	sh "docker push atiskrievinstdl/api-tests-final:latest"
}
