pipeline {
    agent any

    stages {

        stage("cloning the code") {
            steps {
                git branch: 'main', url: 'https://github.com/faizurrahmn-max/spring-petclinic.git'
            }
        }

        stage("building the code") {
            steps {
                sh 'mvn package'
            }
        }

        stage("archiving artifact") {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }

        stage("Junit test Results") {
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }

    }
}
