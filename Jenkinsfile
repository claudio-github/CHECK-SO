def getSo(){
    if(isUnix()){
        return "terraform-linux"
    }else {
            return "terraform-windows"
    }
}


pipeline {

    agent any

    tools {
        "org.jenkinsci.plugins.terraform.TerraformInstallation" getSo()
    }

    environment {
        TF_HOME = tool(getSo())
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
                script{
                echo "terraform version" | sh
                
                }
            }
        }
    }


}