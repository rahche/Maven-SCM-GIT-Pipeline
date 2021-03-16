pipeline { 
agent any 

tools { 
maven "maven3.5" 
} 

stages { 
stage('Build') { 
steps { 

sh "rm -r -f ./Maven-Spring-App" 

git branch: 'main', credentialsId: 'Jenkins-github-user', url: 'https://github.com/rahche/Maven-Spring-App'  
//git url: 'git://github.com/rache/Maven-Spring-App.git', branch: 'main' 


// To run Maven on a Windows agent, use 
sh "mvn -Dmaven.test.failure.ignore=true clean package" 
} 

post { 
success { 
junit '**/target/surefire-reports/TEST-*.xml' 
//archiveArtifacts 'target/*.jar' 
} 
} 
} 
} 
} 
