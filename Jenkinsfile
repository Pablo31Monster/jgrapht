pipeline {
	agent {
		docker {
			image 'maven:3.6.3-openjdk-11'
		}
	}
	stages {
		stage('Build with test') {
			steps {
				sh 'mvn install -DskipTests=true -Dmaven.javadoc.skip=true -B -V'
			}
		}
		stage('Test') {
			 steps {
			 	sh 'mvn verify -B && mvn javadoc:aggregate && mvn checkstyle:check -P checkstyle'
			 }
		}
	}
}
