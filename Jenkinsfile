pipeline{
  agent any

  stages{
    stage('Terraform init'){
      steps{
        sh("terraform init");
       }
    }
    stage('Provisining-AWS-Resources'){
      steps{
        withAWS(credentials: 'awsjenkins', region: 'us-west-2') {
                sh("terraform plan");
                echo "terraform action from parameter is --> ${action}"
                
                }
            }     
       }
     stage('Terraform statelist'){
      steps{
        sh("terraform state list");
       }
    }

}
}

