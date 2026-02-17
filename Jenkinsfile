pipeline {
    agent any
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    triggers {
        pollSCM('* * * * *')
    }
    tools {
        maven 'MAVEN_3.9.12'
    }
    stages {
        stage(' SCM '){
            step {
                git url 'https://github.com/spring-projects/spring-petclinic.git'
                branch ' main '
            }              
        }
        stage ('Build'){
            step {
                sh 'mvn clean package'
            }
        }

    }
}