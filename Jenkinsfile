pipeline {
    agent any

    stages {
        stage('First') {
            steps {
                sh """ssh -tt -i /var/jenkins_home/.ssh/id_rsa root@192.168.1.3 << EOF 
                cd /home/firoz/ && rm -rf Hello_world && mkdir Hello_world && exit
                EOF"""
                
            }
        }
        stage('Second') {
             steps {
               sh '''#!/bin/bash
                 sleep 15
                  '''
    }
        }
        stage('Third') {
            steps {
                sh 'sleep 5'
            }
        }
    }
}
