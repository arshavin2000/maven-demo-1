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
                sh 'mvn install'
            }
        }

        stage ('TEST') {
            steps {
                sh 'mvn test'
            }
        }

        stage ('DEPLOY') {
            steps {
                
            }
        }
        
    }
}
