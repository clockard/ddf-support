pipeline {
  options {
        buildDiscarder(logRotator(numToKeepStr:'25'))
  }
//  triggers {
//    cron('@daily')
//  }
  agent { label 'linux-small' }
  stages {
  stage('Build/UnitTest') {
        node('linux-medium') {
            withMaven(maven: 'Maven 3.3.9', mavenLocalRepo: '.repository') {
                // Compile project
                sh "mvn clean install -B"
            }

        }
    }

    stage('Integration Tests') {
        echo 'Integration Tests'
    }

    stage('Deploy') {
        echo 'Test Deploy'
    }
  }
}
