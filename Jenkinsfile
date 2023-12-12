pipeline {
    agent any 
    stages {
        stage('Clean Workspace') {
            steps {
                deleteDir()
            }
        }

        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/akashrathod7895/webhook-repo3.git']]])
            }
        }

        stage("copyindexfile") {
            steps {
                sh "yum install httpd -y"
                sh "service httpd start"
                sh "chkconfig httpd on"
             sh "cp /root/.jenkins/workspace/project/index.html /var/www/html"
                sh "chmod -R 777 /var"
            }
        }
    }
}
