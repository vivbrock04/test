	pipeline {
	    agent any
	    tools {
	        maven 'Maven_3_5_4'
	        jdk 'JDK_8'
	    }

	    stages {
	        stage('Initialize') {
	            steps {
	                echo "PATH = ${PATH}"
	                echo "M2_HOME = ${M2_HOME}"
	                
	            }
	        }
	        stage('Checkout code') {
	            steps {
	                checkout scm
	            }
	        }

	        stage('Build') {
	            steps {
	                sh 'mvn -Dmaven.test.failure.ignore=true install'
	            }
	            post {
	                success {
	                    junit 'target/surefire-reports/**/*.xml'
	                }
	            }
	        }


	    }
	}