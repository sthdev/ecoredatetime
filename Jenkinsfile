pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat "mvn -B clean compile -DskiptTests=true"
            }
        }
        stage('test') {
            steps {
                bat "mvn -B verify"
            }
            post {
            	always {
            		junit 'test/**/target/surefire-reports/**/*.xml'
            	}
            }
        }
    }
}