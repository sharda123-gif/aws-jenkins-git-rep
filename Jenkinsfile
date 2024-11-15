pipeline {
    agent any
    
    environment {
        AWS_REGION = 'us-east-1'  // Specify the AWS region
    }

    triggers {
    pollSCM('* * * * *') 
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
                        
                        sh 'aws iam list-users'
                        sh 'aws ec2 describe-instances'
                    }
                }
            }
        }
    }
}
