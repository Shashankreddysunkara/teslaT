node{
   stage('Checkout'){
     checkout scm
   }
   stage('Build'){
      // Get maven home path
      sh 'mvn install'
   }
   
   stage('SonarQube Analysis') {        
        withSonarQubeEnv('SonarQube') { 
          sh 'mvn install sonar:sonar'
        }
    }
}
