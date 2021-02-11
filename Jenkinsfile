def repo="https://sahilsethi12.github.io/demo-helm-example/"
pipeline{
		agent{
				label 'helm'
		}
		stages{
				stage("Setup") {
            steps {
               
                    sh "helm repo add sahil ${repo}"
              
            }
        }
				stage("Deploy to Dev") {
            steps {
                script{
										openshift.withCluster(){
                       
                            sh "helm upgrade --install my-guestbook sahil/sample-helm-chart --values sample-helm-chart/values.yaml -n dev --wait"
                        
                    }
                }
            }
        }
				
				
		}

}
