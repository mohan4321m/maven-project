pipeline {
    agent any
    tools {
        maven 'maven'
    }
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
        stage ('Deploy to staging'){
            steps {
            build job: 'deploy-to-staging'
            }
        }    
    }
}
