pipeline {
    agent any

    environment {
        AZURE_SUBSCRIPTION_ID='4917809c-4753-4722-81bf-a1b4429fd9ca'
        AZURE_TENANT_ID='819948b9-e473-435d-b429-6f100444732f'
        
    }

    stages {
        stage('Example') {
            steps {
                   withCredentials([usernamePassword(credentialsId: 'myAzureCredential', passwordVariable: 'AZURE_CLIENT_SECRET', usernameVariable: 'AZURE_CLIENT_ID')]) {
                            sh 'az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t myAzureCredential.AZURE_TENANT_ID'
                       
                       
                       load "${workspace}/resourcegroup.ps1"
                       
                        
                 
                        }
            }
        }
    }
}
