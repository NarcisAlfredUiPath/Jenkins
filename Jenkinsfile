pipeline {   
    agent any      
    stages {  
        stage('Build') {  
            steps {
                sh 'mvn clean install'
                UiPathPack outputPath: '${WORKSPACE}\\Output', projectJsonPath: 'C:\\Users\\narcis.szene\\Documents\\UiPath\\JenkinsTraining', traceLevel: 'None', version: AutoVersion()
                echo 'Build Phase'
            }
        }
        stage('Test') {
            steps {
                echo 'Test Phase'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy Phase'
            }
        }
    }
}
