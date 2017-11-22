pipeline {
  agent any
  stages {
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
          "error": {
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
    stage('Maven Deploy to Artifactory') {
      steps {
        parallel(
          "Maven Deploy to Artifactory": {
            echo 'MavenDeploy'
            
          },
          "Prepare Integration Test Environment": {
            echo 'test environment'
            
          }
        )
      }
    }
    stage('Deploy to integration test environment') {
      steps {
        echo 'test env'
      }
    }
    stage('Run Integration Tests') {
      steps {
        echo 'System tests'
      }
    }
    stage('Release') {
      steps {
        parallel(
          "Github Release Tag": {
            echo 'Release'
            
          },
          "Maven Release Prepare": {
            echo 'Prepare'
            
          },
          "Maven release Perform": {
            echo 'Perform'
            
          }
        )
      }
    }
    stage('Release Stable Branch') {
      steps {
        echo 'Release Stable Branch'
      }
    }
    stage('Maven Release Deploy') {
      steps {
        echo 'Maven Release deploy'
      }
    }
  }
}