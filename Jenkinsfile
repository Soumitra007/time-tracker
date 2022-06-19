#!groovy

pipeline {

  agent any

  environment {
    git_commit_message = ''
    git_commit_diff = ''
    git_commit_author = ''
    git_commit_author_name = ''
    git_commit_author_email = ''
  }

  stage('Compile'){
	             
	              steps{
	                  echo 'compiling..'
	                  bat 'mvn compile'
	             }
	          }
	          stage('CodeReview'){
	                
	              steps{
	                  
	                echo 'codeReview'
	                  bat 'mvn pmd:pmd'
	              }
	          }
	           stage('UnitTest'){
	                
	              steps{
	                
	                  bat 'mvn test'
	              }
	               post {
	               success {
	                   junit 'target/surefire-reports/*.xml'
	               }
	           }   
	          }
	          
	          stage('Package'){
	                
	              steps{
	                
	                  bat 'mvn package'
	              }
	          }
	            
	          
	      }
	}