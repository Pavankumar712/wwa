pipeline {
    agent any

    stages {
        stage('continuous download') {
            steps {
               git 'https://github.com/warofants/wwa.git' 
            }
        }
       stage('continuous build') {
            steps {
               sh 'mvn install'
            }
        } 
        stage('continuous deploy') {
            steps {
               sh 'sshpass -p "pavan" scp target/world-war-of-ants-game-1.0-SNAPSHOT.jar pavan@172.17.0.4:/opt/apache-tomcat-9.0.56/webapps'
            }
        } 
    }
}
