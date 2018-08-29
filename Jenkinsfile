node {
   stage('git') { // for display purposes
      // Get some code from a GitHub repository
      git branch: '2.7', credentialsId: 'Github', url: 'https://github.com/satish736/student-project.git'
   }
   stage('compile') {
      sh 'mvn clean compile'
   }
   stage('code-scan') {
      sh 'mvn sonar:sonar -Dsonar.host.url=http://10.142.0.13:9000 -Dsonar.login=84fc00fbcb1b22bccb072cc83904e997c9832b10'
   }
   stage('deploy-nexus') {
      sh 'mvn package deploy'
   }
}
