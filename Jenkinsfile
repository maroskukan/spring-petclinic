//Declarative //
pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        // implicit checkout stage

        stage('Build') {
            steps {
                // Run Maven Wrapper
                sh './mvnw clean package'
                //sh 'false' // true
            }
        }
    post {
        always {
            junit '**/target/surefire-reports/TEST-*.xml'
            archiveArtifacts 'target/*.jar'
        }
    }
}