pipeline {

    agent any
  
    stages {

        stage('Deploying Resource') {
            steps {
                
                            
                            $cred = New-Object -TypeName System.Management.Automation.PSCredential('21adb328-5bf7-4fd8-b375-dafcc26efa3e' ,'b1m42~j9oo~KGr~lPRrSN0J-kScNoU4of')
 
                           Login-AzureRmAccount -Credential $cred -TenantId '819948b9-e473-435d-b429-6f100444732f'
                            
                            az group create --location westus --resource-group MyResourceGroup
              
             
            }
        }
    }
    
}
