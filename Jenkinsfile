pipeline {
    agent { label 'NODE1_172.31.30.132' }
    options {
        timeout(time: 30, unit: 'MINUTES') 
    }
    triggers { 
        pollSCM('* * * * *')
    }  
    tools {
        jdk 'JDK_17'
    }  
    stages {
        stage ('vcs git ') {
            steps {

                git url: 'https://github.com/muthyalasaikiran/spring-petclinic.git' ,
                    branch: 'main'
            }
        }
        stage ('build and package') {
            steps {
                sh script: 'mvn package'
            }
        }
    }
    }
    