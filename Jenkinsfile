pipeline
{
	agent any
	  stages {
  	      stage('pull'){
                  steps{
                     script{
                         checkout([$class: 'GitSCM', branches: [[name: '*/main']], 
                             userRemoteConfigs: [[ 
                                 credentialsId: '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',
                                 url :'https://github.com/DOMINATORS2020/CD-Project.git']]])
                                 }
			}
                   }
	      stage('build'){
                  steps{
                     script{
                            sh "ansible-playbook /home/mourad/my-app/Ansible/build.yml -i /home/mourad/my-app/Ansible/inventory/host.yml --extra-vars 'ansible_become_pass=mourad'"
                                 }
			}
		}
	}
}
