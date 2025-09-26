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
        
        stage ('reporting and downloads') {
            steps {
                archiveArtifacts artifacts: '**/target/spring-petclinic-*.jar'
                junit testResults: '**/target/surefire-reports/TEST-*.xml'
            }

        }
    }
    post {
        success {
            mail subject: 'your project is successfull',
                 body:    'your project is  effective',
                 to: 'genesys@test.com'
        }
        failure{
            mail subject: 'your project is fail',
                 body:    'your project is  defective',
                 to: 'genesys@test.com'
        }
    }
    }
    