pipeline {
	agent any
	stages {

		stage('kubernetes cluster') {
			steps {
				withAWS(region:'us-east-2', credentials:'MyCredentials') {
					sh '''
						
					'''
				}
			}
		}

		

		stage('Create conf file cluster') {
			steps {
				withAWS(region:'us-east-2', credentials:'MyCredentials') {
					sh '''
						aws eks --region us-east-2 update-kubeconfig --name capstonecluster
					'''
				}
			}
		}

	}
}
