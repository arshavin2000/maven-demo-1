pipeline {
    agent any
    stages {
        stage ('CHECKOUT') {
            steps {
                git branch: 'patch-1', url: "https://github.com/arshavin2000/maven-demo-1.git"
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
