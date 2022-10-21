def getSo(){
    if(isUnix()){
        return "terraform-linux"
    }else {
            return "terraform-windows"
    }
}

def resultado = { cmd -> sh (script: 'echo "Teste com sh"', returnStdout: true).trim()}

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

        stage('Teste script'){
            steps{
                //script{
                    echo resultado
                //}
            }
        }

        stage('Terraform init'){
            steps{
                script{
                    
                }
            }
        }
        
    }


}