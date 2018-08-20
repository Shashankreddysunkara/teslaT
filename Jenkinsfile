node{
   stage('Checkout'){
     checkout scm
   }
   stage('Build'){
      // Get maven home path
      sh 'mvn -U -s settings.xml -gs settings.xml clean install'
   }
   
   stage('SonarQube Analysis') {        
        withSonarQubeEnv('SonarQube') { 
          sh 'mvn sonar:sonar'
        }
    }
}
