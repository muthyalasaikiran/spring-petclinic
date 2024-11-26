pipeline {
    agent { label 'JDK_17' }
    options { 
        timeout(time: 15, unit: 'MINUTES') 
    }
    triggers {
        pollSCM('H */4 * * 1-5') 
           
    }
    tools {
        jdk 'JDK_17'

    }
     stages {
         stage('GIT_cloning') {
            git url : 'https://github.com/muthyalasaikiran/spring-petclinic.git',
                branch : 'main'
     }
        stage('build and package ') {
            sh script : 'mvn package'
     }

        stage('reportingg ') {
            archiveArtifacts artifacts : '**/target/spring-petclinic-*.jar'
            junit testResults :  '**/target/surefire-reports/TEST-*.xml'
     }
    
}

}

