pipeline {
	agent any
		stages{
			stage('Build') {
				steps {
					script{
						sh "ansible-playbook ansible/playbook.yml -i ansible/inventory/Server_host.yml " 
					}
				}
			}
		}
}
 pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[
                            credentialsId: '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',
                            url: 'https://github.com/selimaouini/CI.git']]])
                }
            }
        }
     }
