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


/* syntax used to add assets 
		stage('Assets') {
			steps {
				echo 'Deploying assets...'
				UiPathAssets (
					assetsAction: DeployAssets(), 
					credentials: Token(accountName: 'NarcisOrg', credentialsId: '961a283c-4809-4212-a82c-bb161b2c3d54'), 
					filePath: "C:\\Users\\narcis.szene\\Desktop\\Assets.csv", 
					folderName: 'JenkinsProjects', 
					orchestratorAddress: 'https://cloud.uipath.com/narcisorg/DefaultTenant/orchestrator_/?tid=1159609&fid=3898370', 
					orchestratorTenant: 'DefaultTenant', 
					traceLevel: 'None'
					)
			}
		}
*/
		stage('Test Cases') {
			steps {
				echo 'Performing tests...'
				sh 'pwsh UiPathRunTest.ps1 -orchestrator_url "https://cloud.uipath.com/narcisorg/DefaultTenant/orchestrator_/?tid=1159609&fid=3898370" -orchestrator_tenant DefaultTenant -testset "TestCase1" -UserKey 961a283c-4809-4212-a82c-bb161b2c3d54 -account_name NarcisOrg'
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
