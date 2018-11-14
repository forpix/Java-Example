pipeline {
	agent any
	tools { 
        Maven 'Maven Tool'
	}
	stages  {
		stage ('checkout scm') {
			steps {
				sh '''
				cd /home/mdali/.jenkins/workspace/pipeline-pure/Java-Example
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
			    cd /home/mdali/.jenkins/workspace/pipeline-pure/Java-Example
					mvn compile
					'''
			}
		}
	    stage ('Test') {
			steps {
				sh '''
			    cd /home/mdali/.jenkins/workspace/pipeline-pure/Java-Example
					mvn test
					'''
			}
		}
	    stage ('Package') {
			steps {
				sh '''
			    cd /home/mdali/.jenkins/workspace/pipeline-pure/Java-Example
					mvn package  -DskipTests
					'''
			}
		}
		stage ('Deploy') {
			steps {
				sh '''
			    cd /home/mdali/.jenkins/workspace/pipeline-pure/Java-Example
					mvn install   -DskipTests
					cp /home/mdali/.jenkins/workspace/pipeline-pure/Java-Example/target/Hello.war /home/mdali/Downloads/apache-tomcat-8.5.31/webapps
                    firefox http://localhost:8080/Hello
					'''
			}
		}
	
	    
	}
}
