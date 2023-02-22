pipeline{
    agent any
     environment {
		DOCKERHUB_CREDENTIALS = credentials('DockerHub')
	        GIT_COMMIT = sh(returnStdout: true, script: 'git rev-parse --short HEAD')
	        PORT_app= 9192
	        fname= "demo"
	        USER_DOCKER= 8485012281
                PASS_DOCKER= "Aditya@123"
                IMG_NAME= 'db-application'
	        DB_IMG= 'mysql'
	        MYSQL_PASS= 'root'
	        MYSQL_PORT= 5000
	        docker= sh(script: 'sshpass -p s1 ssh vboxuser@192.168.56.102 docker --version',returnStdout: true)
     }
    stages {
    stage('docker check on remote ') {
	       when { environment name: 'docker', value: '' }
	       steps {
		       echo "${docker}"
		       sh 'ansible-playbook docker-playbook.yml'
	       }
       }  
       
   stage {
   steps{
   
