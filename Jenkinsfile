pipeline
{
		agent any
	          stages {
	              stage('pull') {
	                   steps{
	                      script{
	                      checkout([$class: 'GitSCM', branches: [[name: '*/master']],
	                         userRemoteConfigs: [[
	                             credentialsId: '68733864-97cb-4f48-91fd-bb5eda4e6e87',
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
