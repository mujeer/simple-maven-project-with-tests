pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            } 
        }    
        
        stage('Git Checkout') {
            steps {
                git 'https://github.com/mujeer/pipeline_shell_script.git'
            }
          }
        stage('Run the Shell Script') {
            steps {
                sh '''chmod +x testscript.sh 
                ./testscript.sh > testscript.txt'''
            }  
        }
        stage('ArchivArtifacts') {
            steps {
                archiveArtifacts artifacts: 'testscript.txt', followSymlinks: false
            }  
        }
    }
}
