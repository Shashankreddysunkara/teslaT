pipeline {
    agent { docker { image 'maven:3.3.3' label 'Docker' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
            }
        }
    }
}