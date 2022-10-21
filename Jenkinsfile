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
            when { expression { getOs() == 'terraform-windows' } }
            steps{
                script{
                    echo "Stage do Windows"
                }
            }
        }
        
        stage('Stage do Linux'){
             when { expression { getOs() == 'terraform-linux' } }
            steps{
                script{
                    echo "Stage do Linux"
                }
            }
        }
    }


}