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
                sh("terraform ${action} --auto-approve");

                }
            }     
       }
     stage('Terraform statelist'){
      steps{
        sh("terraform state list");
       }
    }
    stage("copying kubeconfig file to homedirectory"){
      steps{
        sh("terraform output kubeconfig > ~/.kube/config");
       }
    }

}
}

