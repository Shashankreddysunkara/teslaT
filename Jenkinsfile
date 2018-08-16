pipeline {
    agent { 
    	docker { 
   		   image 'maven:3.3.3' 
    	} 
    }
    tools {  
        jdk 'jdk8' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }

        stage ('Build') {
            steps {
                echo 'This is a minimal pipeline.'
                sh 'mvn -Dmaven.test.failure.ignore=true install'
                sh 'echo "mvn- version"'
            }
        }
    }
}
