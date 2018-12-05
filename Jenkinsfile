properties([pipelineTriggers([githubPush()])])

node('linux') {
  stage('Test') {
    git 'https://github.com/damay100/java-project.git'
    sh 'ant -f test.xml -v'
  }
  stage('Build') { 
    sh 'ant -f build.xml -v'
  }
  stage('Results') {
  sh "aws s3 bucket --damay100-assignment11'
    junit 'reports/*.xml'
  }
}


