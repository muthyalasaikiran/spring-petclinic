pipeline {
    agent any
    parameters {
         choice(name: 'CHOICES', choices: ['mvn package', 'mvn test', 'mvn validate'], description: 'this is options') 
         }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('build') {
            steps {
                git url:'https://github.com/muthyalasaikiran/spring-petclinic.git',
                    branch: 'main'
            }
        }
    }
    stage('build') {
            steps {  
                echo "Choice: ${params.CHOICES}" 
            

            }
    }

}