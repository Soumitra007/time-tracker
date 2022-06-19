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

  stages {

    // Build
    stage('Build') {
      
      steps {
        deleteDir()
        checkout scm
      }
    }

    // Static Code Analysis
    stage('Code Review') {
     
      steps {
        deleteDir()
        checkout scm
        echo 'Run Code Review Analysis'
      }
    }

    // Unit Tests
    stage('Unit Tests') {
      
      steps {
        deleteDir()
        checkout scm
        echo 'Run Unit Tests'
      }
    }

    // Package
    stage('Package') {
      
      steps {
        deleteDir()
        checkout scm
        echo 'Run Package Tests'
      }
    }

  }
  post {
    success {
      echo 'Send mail on success'
      // mail to:"me@example.com", subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed."
    }
    failure {
      echo 'Send mail on failure'
      // mail to:"me@example.com", subject:"FAILURE: ${currentBuild.fullDisplayName}", body: "Boo, we failed."
    }
  }
}