node{
   stage('SCM Checkout'){
     git 'https://github.com/inusasunny/teslaT'
   }
   stage('Build'){
      // Get maven home path
      def mvnHome =  tool name: 'Maven 3.5.4', type: 'maven'   
      sh "${mvnHome}/bin/mvn install"
   }
   
   stage('SonarQube Analysis') {
        def mvnHome =  tool name: 'Maven 3.5.4', type: 'maven'
        withSonarQubeEnv('SonarQube') { 
          sh "${mvnHome}/bin/mvn sonar:sonar"
        }
    }
   
   stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      sunny''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: '3605092@gmail.com'
   }
}
