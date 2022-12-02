pipeline {    
    agent any      
    stages {  
        stage('Build') {  
            steps {
                echo 'Starting packaging...'
                UiPathPack 
                (
                 outputPath: "${WORKSPACE}\Output", 
                 projectJsonPath: "project.json", 
                 traceLevel: 'None', 
                 version: AutoVersion()
                )
                echo 'Packaging ended' 
            }
        }
    }
}
