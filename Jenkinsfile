pipeline {
    agent any
    
    environment {
        AWS_REGION = 'us-east-1'  // Specify the AWS region
    }

    stages {
        stage('List S3 Buckets') {
            steps {
                script {
                    withCredentials([[
     $class: 'AmazonWebServicesCredentialsBinding',
      credentialsId: 'aws-jenkins-demo', 
      accessKeyVariable: 'AWS_ACCESS_KEY_ID',
      secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) 

 {
                        sh 'aws s3 ls'
                        sh 'aws iam list-users'
                    }
                }
            }
        }
    }
}
