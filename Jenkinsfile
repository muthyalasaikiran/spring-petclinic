node('JDK11MVN') {
    stage('vcs') {
        git branch: 'REL_INT_1.0', url: 'https://github.com/GitPracticeRepo/spring-petclinic.git'
    }
    stage("build") {
        sh '/opt/apache-maven-3.8.7/bin/mvn package'
    }
    stage("archive results") {
        junit '**/surefire-reports/*.xml'

    }
}