pipeline {    
    agent any      
    stages {  
        stage('Build') {  
            steps {
                echo 'Starting packaging...'
                UiPathPack outputPath: '${WORKSPACE}\\Output', projectJsonPath: 'C:\\Users\\narcis.szene\\Documents\\UiPath\\JenkinsTraining', traceLevel: 'None', version: AutoVersion()
                echo 'Packaging ended'
            }
        }
    }
}
