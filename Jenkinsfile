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
                         scripts{
                         sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
                                }
                        }
        }
     }
  }
