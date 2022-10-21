def getSo(){
    if(isUnix()){
        return "Linux SO"
    }else {
            return "Windows SO"
    }
}


pipeline {

    agent any

    tools {
        "org.jenkinsci.plugins.terraform.TerraformInstallation" "terraform"
    }

    environment {
        TF_HOME = tool('terraform')
        TF_IN_AUTOMATION = "true"
        PATH = "$TF_HOME:$PATH"
    }


    stages {
        stage('check so'){
            steps{
                echo getSo()
            }
        }

        stage('Terraform Version'){
            steps{
                terraform version
            }
        }
    }


}