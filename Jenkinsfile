pipeline {

    agent any
  
    stages {

        stage('Deploying Resource') {
            steps {
                
                            
                            az login --service-principal -u '21adb328-5bf7-4fd8-b375-dafcc26efa3e' -p 'b1m42~j9oo~KGr~lPRrSN0J-kScNoU4of' --tenant '819948b9-e473-435d-b429-6f100444732f' | Out-null
                            
                            az group create --location westus --resource-group MyResourceGroup
              
             
            }
        }
    }
    
}
