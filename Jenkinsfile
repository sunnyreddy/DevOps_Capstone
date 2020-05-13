pipeline {
	agent any
	stages {

		stage('kubernetes cluster') {
			steps {
				withAWS(region:'us-east-2', credentials:'MyCredentials') {
					sh '''
						eksctl create cluster \
						--name capstonecluster \
						--version 1.13 \
						--nodegroup-name standard-workers \
						--node-type t2.small \
						--nodes 2 \
						--nodes-min 1 \
						--nodes-max 3 \
						--node-ami auto \
						--region us-east-2 \
						--zones us-east-2a \
						--zones us-east-2b \
						--zones us-east-2c \
					'''
				}
			}
		}

		

		stage('Create conf file cluster') {
			steps {
				withAWS(region:'us-east-2', credentials:'MyCredentials') {
					sh '''
						awscli --version
						aws eks --region us-east-2 update-kubeconfig --name capstonecluster
					'''
				}
			}
		}

	}
}
