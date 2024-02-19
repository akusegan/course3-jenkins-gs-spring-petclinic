echo "Hello World"

pipeline {
    agent any
    
    stages {
        stage("checkout") {
            steps {
                sh "ls"
                git branch:'main', url: 'https://github.com/akusegan/course3-jenkins-gs-spring-petclinic'
                sh "ls"
            }
        }
        
        stage("build"){
            steps {
                sh "./mvnw package"
            }
        }
        
        stage("capture") {
            steps {
                // **/target/*.jar
                archiveArtifacts '**/target/*.jar'
                junit '**/target/surefire-reports/TEST*.xml'
                jacoco()
            }
        }
    }
}