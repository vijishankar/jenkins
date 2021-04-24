pipeline {
    agent any
    parameters {
        
        string(name: 'PROJECT', defaultValue: '', description: 'Project Name')
        choice(name: 'ENVIRONMENT', choices: ['Dev', 'Test', 'stage', 'Uat', 'Sit', 'Prod'], description: 'Environment')
        
        
        
        booleanParam(name: 'Delete_CoreResources', defaultValue: 'false', description: '')
        booleanParam(name: 'Delete_IngressResources', defaultValue: 'false', description: '')
        booleanParam(name: 'Delete_TransactResources', defaultValue: 'false', description: '')
        booleanParam(name: 'All', defaultValue: false, description: 'Deploy all resrouces')
        
        
         //string(name: 'RGName', defaultValue: '', description: 'Azure RG Name')
    }
    
    environment {
       
       AZURE_SUBSCRIPTION_ID='4917809c-4753-4722-81bf-a1b4429fd9ca'
        AZURE_TENANT_ID='819948b9-e473-435d-b429-6f100444732f'
         WORKSPACE = "$environment-$PROJECT"
        RG = ""
        
    }

    stages {
        stage('Example') {
            steps {
                   withCredentials([usernamePassword(credentialsId: 'myAzureCredential', passwordVariable: 'AZURE_CLIENT_SECRET', usernameVariable: 'AZURE_CLIENT_ID')]) {
                            sh 'az login --service-principal -u $AZURE_CLIENT_ID -p $AZURE_CLIENT_SECRET -t $AZURE_TENANT_ID'
                       
                  
                       println "${WORKSPACE}"
                       script{
                       if ("${RG}" -eq ('Delete_CoreResources'))
                       {
                           println "Delete_CoreResources"
                       }
                       }
                        
                      //sh'az deployment group create e --resource-group "Testgroup" --template-file  "${workspace}/Storage.json" --parameters  "${workspace}/Storage.Parameters.json"'
  
   
 
  
                       
         
                       
                    
                       
                       
                        }
            }
        }
    }
}
