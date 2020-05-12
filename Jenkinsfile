pipeline {
	agent any
	stages {

		stage('kubernetes cluster') {
			steps {
				withAWS(region:'us-east-2', credentials:'MyCredentials') {
					sh '''
						eksctl create cluster \
						--name capstonecluster \
						--version 1.12 \
						--nodegroup-name standard-workers \
						--node-type t2.small \
						--nodes 2 \
						--nodes-min 1 \
						--nodes-max 3 \
						--node-ami auto \
						--region us-east-2 \
						--zones us-east-1a \
						--zones us-east-1b \
						--zones us-east-1c \
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
