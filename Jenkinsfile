pipeline {
    agent any
    stages{
        stage('Build'){
            steps {  
                sh 'localmaven clean package'
            }    
            post {
                success {
                    echo 'Now Archiving..'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }   
        }
    }
}
