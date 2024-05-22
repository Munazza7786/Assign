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
export PROJECT=$(gcloud info --format='value(config.project)')
export SA_EMAIL=$(gcloud iam service-accounts list --filter="name:jenkins-gce" \
 --format='value(email)')
gcloud projects add-iam-policy-binding --member serviceAccount:$SA_EMAIL \
 --role roles/compute.instanceAdmin $PROJECT
gcloud projects add-iam-policy-binding --member serviceAccount:$SA_EMAIL \
 --role roles/compute.networkAdmin $PROJECT
gcloud projects add-iam-policy-binding --member serviceAccount:$SA_EMAIL \
 --role roles/iam.serviceAccountUser $PROJECT
 gcloud projects get-iam-policy $PROJECT
