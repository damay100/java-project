properties([pipelineTriggers([githubPush()])])

node('linux') {
  stage('Test') {
    git 'https://github.com/<github_username>/java-project.git'
    sh 'ant -f test.xml -v'
  }
  stage('Build') { 
    sh 'ant -f build.xml -v'
  }
  stage('Results') {
    junit 'reports/*.xml'
  }
}


