pipeline {
    agent any

    environment {
        AZURE_SUBSCRIPTION_ID= credentials('AZURE_SUBSCRIPTION_ID')
        AZURE_TENANT_ID= credentials('AZURE_TENANT_ID')
        
    }

    stages {
        stage('Example') {
            steps {
                   withCredentials([usernamePassword(credentialsId: 'myAzureCredential', passwordVariable: 'AZURE_CLIENT_SECRET', usernameVariable: 'AZURE_CLIENT_ID')]) {
                            sh 'az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID'
                       
                       
                       load "${workspace}/resourcegroup.json"
                       
                        
                 
                        }
            }
        }
    }
}
