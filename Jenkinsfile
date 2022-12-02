pipeline {   
    agent any      
    stages {  
        stage('build') {  
            steps {
                UiPathPack outputPath: '${WORKSPACE}\\Output', projectJsonPath: '${WORKSPACE}', traceLevel: 'None', version: AutoVersion()
            }
        }
    }
}
