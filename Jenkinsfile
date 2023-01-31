pipeline {
    agent any

    tools {
        maven "MY_MAVEN"
    }

    stages {
        stage ('clean') {
            steps {
                dir('./backend') {
                    sh 'rm target/ROOT.war'
                    sh 'mvn clean'
                }
        }
        }
        stage ('test') {
            steps {
                sh 'mvn test -f ./backend' 
            }
            
        }
         stage ('packagin in to war') {
            steps {
                sh 'mvn war:war -f ./backend' 
            }
            
        }
        stage ('deploy') {
            steps {
                dir('./backend'){
                    docker cp 'tartget/ROOT.war' './webapps'
                }
            }
            
        }
    }
}
