pipeline {
	agent any
	tools { 
        maven 'maven'
	}
	stages  {
		stage ('checkout scm') {
			steps {
				sh '''
				pwd;ls -a
				git remote update 
				git pull origin master
				echo "PATH = ${PATH}"
                echo "M2_HOME = ${M2_HOME}"
				
				pwd;ls
				'''
			}
		}
		stage ('compile') {
			steps {
				sh '''
				pwd;ls -a
					mvn compile
					'''
			}
		}
	    stage ('Test') {
			steps {
				sh '''
					mvn test
					'''
			}
		}
	    stage ('Package') {
			steps {
				sh '''
					mvn package  -DskipTests
					'''
			}
		}
		stage ('Deploy') {
			steps {
				sh '''
					mvn install   -DskipTests
					cp /home/mdali/.jenkins/workspace/pipeline-pure/Java-Example/target/Hello.war /home/mdali/Downloads/apache-tomcat-8.5.34/webapps
                    firefox http://localhost:8080/Hello
					'''
			}
		}
	
	    
	}
}
