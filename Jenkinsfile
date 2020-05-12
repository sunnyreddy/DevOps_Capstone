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
						sudo apt-get remove --auto-remove awscli
						ln -s /home/ubuntu/.local/bin/aws /usr/bin/aws
						pip install awscli --upgrade
						awscli --version
						aws eks --region us-east-2 update-kubeconfig --name capstonecluster
					'''
				}
			}
		}

	}
}
