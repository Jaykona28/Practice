pipeline{
   agent any
   environment{
      PATH="$PATH:/opt/maven/bin"
	 }
	 stages{
	   stage('GetCode'){
	     steps{
		   git branch: 'main', url: 'https://github.com/Jaykona28/Practice.git'
		  }
		}
       stage('Build'){
          steps{
            sh 'mvn clean package'
            }
		   }
	   stage('SonarQube analysis'){
       steps{
	   withSonarQubeEnv('Sonar-Server-9.9.8'){
	      sh "mvn sonar:sonar"
	     }
		 }
		 } 
		}
	   } 
