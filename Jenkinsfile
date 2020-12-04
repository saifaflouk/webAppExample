pipeline {    
         
	agent any
    stages {
        stage("Delete Workspace"){
            steps {                 
                cleanWs deleteDirs: true
				        checkout scm
            }
        }
		
        stage("Build Application"){           
          steps {
            bat '''
            mvn clean package 
            '''
          }     
        }
         
    }
    post {
            always {
               deploy adapters: [tomcat9(credentialsId: '3e300702-b001-4b27-9aab-592eb7d520bf', path: '', url: 'http://localhost:8091')], contextPath: 'App', onFailure: false, war: '**/*.war'
            }
    }
}
