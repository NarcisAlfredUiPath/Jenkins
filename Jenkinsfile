pipeline {    
    agent any      
    stages {  
        stage('Build') {  
            steps {
                echo 'Starting packaging...'
                UiPathPack outputPath: '${WORKSPACE}\Process\Output', projectJsonPath: '${WORKSPACE}', traceLevel: 'None', version: AutoVersion()
                echo 'Packaging ended' 
            }
        }
    }
}
