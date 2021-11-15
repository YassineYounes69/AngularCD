pipeline
{
		agent any
	          stages {
	              stage('pull) {
	                   steps{
	                      script{
	                      checkout([$class: 'GitSCM', branches: [[name: '*/master']],
	                         userRemoteConfigs: [[
	                             credentialsId: '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',
	                             url: 'https://github.com/Ahmed1889/AngularCD.git']]])
	                             }
	                             }
	                             }
	          }
}
