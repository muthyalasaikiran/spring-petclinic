pipeline {
    agent any 
    triggers { pollSCM('* * * * *') }
    tools {
         jdk 'JDK_17'
         maven 'MVN_ 3.9.12'
    }
    parameters { choice(name: 'CHOICES', choices: ['mvn package', 'mvn validate', 'mvn clean','mvn test'], description: '') }
    stages {
        stage('git clone'){
            steps {
                git branch:'main',url:'https://github.com/muthyalasaikiran/spring-petclinic.git'
            }
        }
        stage('validate'){
            steps{
                echo "Choice: ${params.CHOICES}"
            }
        }

    }
}