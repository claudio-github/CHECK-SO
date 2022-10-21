def getSo(){
    if(isUnix()){
        return "Linux SO"
    }else {
            return "Windows SO"
    }
}


pipeline {

    agent any
    stages {
        stage('check so'){
            steps{
                echo getSo()
            }
        }
    }


}