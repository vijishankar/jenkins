pipeline {

    agent any
    environment {
        AZURE_CLIENT_ID = '21adb328-5bf7-4fd8-b375-dafcc26efa3e'
        AZURE_CLIENT_SECRET = 'b1m42~j9oo~KGr~lPRrSN0J-kScNoU4of'
        AZURE_TENANT_ID = '819948b9-e473-435d-b429-6f100444732f'
        APP_URL = 'http://azure-cli-2020-12-31-10-08-57'
    }

    stages {

        stage('Deploying Resource') {
            steps {
                
                   
                            
                            
                            az login --service-principal -u $APP_URL -p $AZURE_CLIENT_SECRET --tenant $AZURE_TENANT_ID | Out-null
                            
                            az group create --location westus --resource-group MyResourceGroup
              
             
            }
        }
    }
    
}
