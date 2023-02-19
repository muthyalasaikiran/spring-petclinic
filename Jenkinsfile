pipeline {
    agent any
    stages {
        stage ('vcs') {
            steps {
                 git branch: 'main', url: 'https://github.com/muthyalasaikiran/spring-petclinic.git'
               
            }
            
        }
        stage ('mvn') {
            steps {
                sh 'mvn clean'
                sh 'mvn package'
            }   
        }
        
    }
}    
