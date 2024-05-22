pipeline {
    agent any
    
    tools {
        jdk 'JDK11' 
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Application build stage...' 
                sh 'javac program.java'
        }
       }
        stage('Test') {
            steps {
                echo 'Application test stage' 
        }
        }
        stage('Run') {
            steps {
                echo 'Application run stage' 
                sh 'java program'
            }
        }
    }
}
echo "This is my IP"
curl -s ifconfig.co
echo "This is my hostname"
hostname -f

