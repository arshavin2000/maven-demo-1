pipeline {
    agent any
    environment {
        mvn = "$MAVEN_HOME/bin/mvn"
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
                sh 'mvn test'
            }
        }


        
    }
}
