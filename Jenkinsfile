pipeline {
    agent any
    stages{
        stage('clone the repo and removing the existing one')
        {
          steps {
              bat "cd d:\dev\packtpub\develop-and-deploy-modern-web-applications-with-docker"
              bat "IF exist jenkins-pipeline (rmdir /s /q jenkins-pipeline)"
              bat "git clone https://github.com/shayim/Develop-and-Deploy-Modern-Web-Applications-with-Docker-Video-.git jenkins-pipeline"
               }
         }
         
         stage("copying files to /var/www/html")
         {
           steps 
           {
              sh "sudo cp /home/coreopt1/project/www/html/index.html /var/www/html/"
           }
          }
          
           stage("Installing the webserver and starting its service")
          {
            steps
            {
              sh "sudo apt install apache2 -y"
              sh "sudo systemctl start apache2"
            }
          }
          
          
          stage("Restarting the apache2 service")
          {
            steps
            {
              sh "sudo systemctl restart apache2"
            }
          }
               
    }

}
