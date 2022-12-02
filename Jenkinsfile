pipeline {   
    agent any      
    stages {  
        stage('build') {  
            steps {
                UiPathPack outputPath: '${WORKSPACE}\\Output', projectJsonPath: 'C:\\Users\\narcis.szene\\Documents\\UiPath\\JenkinsTraining', traceLevel: 'None', version: AutoVersion()
            }
        }
    }
}
