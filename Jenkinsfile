pipeline {    
    agent any      
    stages {  
        stage('Build') {  
            steps {
                echo 'Starting packaging...'
                UiPathPack (
                    outputPath: "${WORKSPACE}\\Output", 
                    projectJsonPath: "project.json", 
                    traceLevel: 'None',
                    version: AutoVersion()
                    )
            }
        }
        stage('Deploy') {
            steps {
                echo 'Starting deployment...' 
                UiPathDeploy (
                    createProcess: false, 
                    credentials: Token(accountName: 'NarcisOrg', credentialsId: '961a283c-4809-4212-a82c-bb161b2c3d54'), 
                    entryPointPaths: 'Main.xaml', 
                    environments: '', 
                    folderName: 'JenkinsProjects', 
                    orchestratorAddress: 'https://cloud.uipath.com/narcisorg/DefaultTenant/orchestrator_/?tid=1159609&fid=3898370', 
                    orchestratorTenant: 'DefaultTenant', 
                    packagePath: "${WORKSPACE}\\Output", 
                    traceLevel: 'None' 
                    )
            }
        }
    }
    post {
	        always {
	            /* Cleans workspace */
	            cleanWs()
	        }
    }
}
