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
        stage('Build')
{
                  steps {
                         script{
                         sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
                 }
             }
        }

        
     }
  }
