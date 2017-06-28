#!/usr/bin/env groovy
node('slave') {
    @Library('jenkins-library') _
    step([$class: 'WsCleanup'])
    sshagent(credentials: ['JenkinsDeployKey']) {
      stage('CHECKOUT') {
        checkout scm
      }
      def _git = new org.jenkins.Git()
      tagName = _git.getTagName()
    }
    stage('Build') {
      echo 'Tag is: "' + tagName + '"'
    }
}
