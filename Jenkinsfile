echo "Hello World"

pipeline {
    agent any
    
    stages {
       
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