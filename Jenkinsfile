node {
    def mvnHome
    stage('Preparation') { // for display purposes
        // Get some code from a GitHub repository
        git 'https://github.com/ishaikhfiroz/basic_test.git'
        // Get the Maven tool.
        // ** NOTE: This 'M3' Maven tool must be configured
        // **       in the global configuration.
        //mvnHome = tool 'M3'
    }
    stage('Build') {
        // Run the maven buildsteps 
        steps {
         sh '''#!/bin/bash
                 rsync -auvz -e "ssh -i /var/jenkins_home/.ssh/id_rsa" . root@192.168.1.3:/var/www/html/basic_test
                 ssh -tt -i /var/jenkins_home/.ssh/id_rsa root@192.168.1.3 <<'ENDSSH'
                 cd /var/www/html && chown -R www-data:www-data basic_test/ && exit
                 exit
         '''
        }
        
            }
    stage('Results') {
        steps {
         sh '''#!/bin/bash
                 echo "Deploy success" 
         '''
        }
    }
}
