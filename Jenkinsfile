pipeline {
    agent { label 'SPC_NODE1' }
    triggers { pollSCM('* * * * *') }
    parameters { choice(name: 'CHOICES', choices: ['mvn clean', 'mvn package', 'mvn validate'], description: '') }
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    tools {
        jdk 'JDK_17'
        maven 'mvn_3.9.12'
    }
    stages{
        stage('git clone') {
            steps {
                git branch: 'main', url: 'https://github.com/muthyalasaikiran/spring-petclinic.git'
            }
            
        }

        stage('validate the codde') {
            steps {
                echo "Choice: ${params.CHOICES}"
            }
        }
    }
  
}