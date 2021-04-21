pipeline {

    agent any
    environment {
        AZURE_CLIENT_ID = credentials('AZURE_CLIENT_ID')
        AZURE_CLIENT_SECRET = credentials('AZURE_CLIENT_SECRET')
        AZURE_TENANT_ID = credentials('AZURE_TENANT_ID')
        APP_URL = credentials('APP_URL')
    }

    stages {

        stage('Deploying Resource') {
            steps {
                container('azure') {
                    pwsh ''' 
                            ############################### Powershell #############################
                            
                            $passwd = ConvertTo-SecureString $env:AZURE_CLIENT_SECRET -AsPlainText -Force
                            $pscredential = New-Object System.Management.Automation.PSCredential($env:AZURE_CLIENT_ID, $passwd)
                            Connect-AzAccount -ServicePrincipal -Credential $pscredential -Tenant $env:AZURE_TENANT_ID | Out-null
                            #Write-Output "Azure Subscription is "$Env:AZSUBSCRIPTION""
                            Select-AzSubscription -Subscription "$Env:AZSUBSCRIPTION" | Set-AzContext | Out-null
                            
                            az login --service-principal -u $Env:APP_URL -p $Env:AZURE_CLIENT_SECRET --tenant $Env:AZURE_TENANT_ID | Out-null
                            
                            az group create --location westus --resource-group MyResourceGroup
                '''
                }
            }
        }
    }
    post {
        always {
            echo "\u001B[43;1m Total Build Duration is ${currentBuild.durationString.minus(' and counting')}\u001B[0m"
        }
    }
}
