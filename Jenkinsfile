pipeline {
    agent any
    
    environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "54.154.62.158:8081"
        NEXUS_REPOSITORY = "maven-public"
        NEXUS_CREDENTIAL_ID = "sonar-admin"
    }
    stages {
        stage ('CHECKOUT') {
            steps {
                git branch: 'master', url: "https://github.com/arshavin2000/maven-demo-1.git"
            }
        }

        
        stage ('BUILD') {
            steps {
                sh 'source ~/.bash_profile && mvn install'
            }
        }
    
        stage ('TEST') {
            steps {
                sh 'source ~/.bash_profile && mvn test'
            }
        }

      
        
    }
    post {
        always {
            
            echo 'I will always say Hello again!'
            
            emailext body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
                recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']],
                subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}"
        }
    }
    
    
    
    

}
