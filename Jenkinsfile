pipeline{
  agent any
  environment {
    PATH = "${PATH}:${getTerraformPath()}"
  }
  stages{
    stage('terraform init and apply - dev'){
      steps{
        sh returnStatus: true, script: 'terraform workspace new dev'
        sh "terraform init"
       }
    }

  }
}

def getTerraformPath(){
  def tfHome = tool name: 'Terraform v0.12.7', type: 'org.jenkinsci.plugins.terraform.TerraformInstallation'
  return tfHome
}
