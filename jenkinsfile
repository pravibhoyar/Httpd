pipeline {
  agent {
        label {
		
		    label "slave-1"
			customWorkspace "/mnt/vol1"
		}
  }
  stages {
    stage('Deploy to Container-1') {
	    steps {
	       sh "sudo docker stop container-1"
               sh "sudo docker rm container-1"
	       sh "sudo docker volume create my-volume-1"
	       sh "sudo cp /mnt/vol1/index.html /var/lib/docker/volumes/my-volume-1/_data"
	       sh "sudo docker run -itdp 80:80 -v my-volume-1:/usr/local/apache2/htdocs --name container-1 httpd"
	      
      }
    }
  }
}
