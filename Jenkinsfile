pipeline{
  agent any

  stages{
    stage('Provisining-AWS-Resources'){
      steps{
        withAWS(credentials: 'awsjenkins', region: 'us-west-2') {

                echo "terraform action from parameter is --> ${action}"
                sh ("terraform ${action} --auto-approve");
                }
            }
    }
  }
}

