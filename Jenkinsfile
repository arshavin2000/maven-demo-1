pipeline {
    agent any
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
}
