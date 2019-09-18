pipeline {
   agent any
   stages {
       stage('git') {
           steps {
                git 'https://github.com/rymarczm/spring-demo'
           }
       }
       stage('build') {
           steps {
               timestamps {
                ansiColor('xterm') {
                               bat label: '', script: 'mvn clean package'
                }
               }
 
           }
       }
       stage('report') {
           steps {
                junit '**/target/surefire-reports/*.xml'
           }
       }
       
   }
}
