pipeline {   
    agent any      
    stages {  
        stage('Build') {  
            steps {
                UiPathPack outputPath: '${WORKSPACE}\\Output', projectJsonPath: 'C:\\Users\\narcis.szene\\Documents\\UiPath\\JenkinsTraining', traceLevel: 'None', version: AutoVersion()
                echo 'Build Phase'
            }
        }
    }
}
