pipeline
{
		agent any
	          stages {
	              stage('pull') {
	                   steps{
	                      script{
	                      checkout([$class: 'GitSCM', branches: [[name: '*/main']],
	                         userRemoteConfigs: [[
	                             credentialsId: '8bb491df-8704-4cee-89c4-566af4652c19',
	                             url: 'https://github.com/YassineYounes69/AngularCD.git']]])
	                             }
	                             }
	                             }
	              /*stage('Build'){
	              steps{
	              script {
	                      		sh "sudo -S ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "
	                      }
	                      }
	                      }*/
	                stage('docker'){
	                      steps {
	                      sh "sudo -S ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml "
	                      }
	                }
	                stage('docker hub'){
	                      steps {
	                      sh "sudo -S ansible-playbook Ansible/docker-registry.yml -i Ansible/inventory/host.yml "
	                      }
	                }
	          }
}
