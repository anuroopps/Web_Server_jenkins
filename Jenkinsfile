pipeline{
   agent any
   stages{
	stage('path')
	{
           steps{
              sh 'pwd'
	   }
	}
	   
	stage('clean workspace')
	{
           steps{
              sh ' rm -r *'
			//   cleaning workspace in www/html/*     i.e, index.html file in html folder
			//   rm -r /var/lib/jenkins/workspace/htlm_project/www/html
			
	   }
	}
	stage('get scm')
	{
           steps{
			// cloning project into jekins/workspace/     this process happens everytime
              sh ' git clone https://github.com/anuroopps/Web_Server_jenkins.git -b main'
	   }
	}
	stage('deploy')
	{
           steps{
		   sh 'sudo chown jenkins:jenkins ../../../www/html'
			// now moving the project back into var/www/html
              sh ' mv html_project/* ../../../../www/html '
	   }
	}
   }
}
