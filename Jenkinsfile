@Library('my-shared-library@main') 

pipeline {
    agent { label 'slave' }

    environment {
        JAVA_HOME = '/usr/lib/jvm/java-17-openjdk-amd64'
        MAVEN_HOME = '/usr/share/maven'
        PATH = "${JAVA_HOME}/bin:${MAVEN_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Run Full Pipeline') {
            steps {
                script {
                    deployApp.runFullPipeline('target/parcel-service-1.0-SNAPSHOT.jar') 
                }
            }
        }
    }

    post {
        always {
            echo 'Cleanup tasks completed.'
        }
    }
}
