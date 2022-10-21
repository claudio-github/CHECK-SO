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

        stage('Primeiro Stage'){
            steps{
                script{
                    echo "Iniciando a Pipeline"
                }
            }
        }

        stage('Stage do Windows'){
            steps{
                script{
                    echo "Stage do Windows"
                }
            }
        }
        
        stage('Stage do Linux'){
            steps{
                script{
                    echo "Stage do Linux"
                }
            }
        }
    }


}