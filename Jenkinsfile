pipeline {    
    agent any      
    stages {  
        stage('Build') {  
            steps {
                echo 'Starting packaging...'
                UiPathPack outputPath: '${WORKSPACE}\Process\Output\${BUILD_NUMBER}', projectJsonPath: 'C:\\Users\\narcis.szene\\Documents\\UiPath\\JenkinsTraining', traceLevel: 'None', version: AutoVersion()
                echo 'Packaging ended' 
            }
        }
    }
}
