pipeline {
    agent any 
    triggers { pollSCM('* * * * *') }
    parameters { choice(name: 'CHOICES', choices: ['mvn package', 'mvn validate', 'mvn clean','mvn test'], description: '') }
    stages {
        stage('git clone'){
            steps {
                git branch:'main',url:'https://github.com/muthyalasaikiran/spring-petclinic.git'
            }
        }
        stage('validate'){
            steps{
                sh 'mvn --version'
                sh 'mvn validate'
            }
        }

    }
}