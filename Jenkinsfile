pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/viplav/Documents/maven/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/flipkart.war /home/viplav/Documents/maven/apache-tomcat-9.0.88/webapps'
			}}	
}}
