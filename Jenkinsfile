pipeline {
    agent any

    stages {
       stage('Pull') {
			steps{
			script{
				checkout([$class: 'GitSCM' , branches: [[name: '*/master']],
					userRemoteConfigs: [[ 
					url: 'https://github.com/BenkraiemSiwar/Projet_CD.git']]])
				}
			}
		}
	stage('build') {
	    	       steps{
	     		   script{
	     		       
	          		sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
	           }
	        }
	    }
}
}
