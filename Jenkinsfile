pipeline {
  agent any
  stages {
    stage('Tools Install') {
      steps {
        echo 'Tool Installation'
      }
    }
    stage('Checkout') {
      steps {
        echo 'Checkout'
      }
    }
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'Build'
            
          },
          "SonarQube Analysis": {
            echo 'sonarQube Analysis'
            
          },
          "Run Unit Tests": {
            echo 'Run Unit Tests'
            
          },
          "Password Scan": {
            echo 'Password Scan'
            
          },
          "Validate Files (Jenkins, docker, Codacy)": {
            echo 'Jenkins file'
            
          },
          "": {
            echo 'Files'
            
          }
        )
      }
    }
    stage('Open Source Readiness Checks') {
      steps {
        parallel(
          "Third Party Library Approvals": {
            echo 'Opens Source readiness'
            
          },
          "Security Scan": {
            echo 'Security Scan'
            
          },
          "Check POM File Contents": {
            echo 'POM Content'
            
          },
          "Check Valid License file": {
            echo 'Valid License File'
            
          },
          "Check Readme file Contents": {
            echo 'readme'
            
          },
          "Check ChangeLog File and contents": {
            echo 'ChangeLog'
            
          },
          "Check Badges": {
            echo 'Badges'
            
          },
          "Check CopyRight information": {
            echo 'CopyRight'
            
          }
        )
      }
    }
    stage('Maven Deploy to Maven Repository or Maven Central') {
      steps {
        echo 'MavenDeploy'
      }
    }
  }
}