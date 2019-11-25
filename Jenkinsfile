pipeline {
  agent any
  stages {
    stage('AWS Credentials') {
      steps {
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AKIAU6I3LYWXD6ZIDYV4', credentialsId: 'AWS', secretKeyVariable: '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']]) {
          sh """
                  mkdir -p ~/.aws
                  echo "[default]" >~/.aws/credentials
                  echo "[default]" >~/.boto
                  echo "aws_access_key_id = ${AWS_ACCESS_KEY_ID}" >>~/.boto
                  echo "aws_secret_access_key = ${AWS_SECRET_ACCESS_KEY}">>~/.boto
                  echo "aws_access_key_id = ${AWS_ACCESS_KEY_ID}" >>~/.aws/credentials
                  echo "aws_secret_access_key = ${AWS_SECRET_ACCESS_KEY}">>~/.aws/credentials
          """
        }
      }
    }

    stage('Create EC2 Instance') {
      steps {
        ansiblePlaybook playbook: 'main.yaml', inventory: 'inventory'
      }
    }
  }
}
