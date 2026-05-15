pipeline {
    agent any
    parameters { choice(name: 'CHOICES', choices: ['mvn test', 'mvn clean', 'mvn validate', 'mvn package'], description: 'this is build parameter') }
    tools {
        maven 'MVN_3.9.12'
        jdk 'JDK_17'
    }
    triggers { 
        pollSCM('* * * * *')
         }
    stages {
        stage ('update and install'){
            steps {
            sh "sudo apt update"
            sh "sudo apt install openjdk-17-jdk maven -y "
            }
        }
        stage ('git clone' ) {
            steps {
           git branch: 'main', url: 'https://github.com/muthyalasaikiran/spring-petclinic.git'
            }
        }

        stage ('build') {
            steps{
              sh '$CHOICES'
           }
        }
    }
}