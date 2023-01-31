pipeline {
    agent any

    tools {
        maven "MY_MAVEN"
    }

    stages {
        stage ('clean') {
            steps {
                dir('./backend') {
                    sh 'rm -r ./target/ROOT.war'
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

                    echo 'working'
                }
            }
            
        }
    }
}
