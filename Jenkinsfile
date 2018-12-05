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
  s3Upload consoleLogLevel: 'INFO', dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'damay100-assignment11', excludedFile: '', flatten: false, gzipFiles: false, keepForever: false, managedArtifacts: false, noUploadOnFailure: false, selectedRegion: 'us-east-1', showDirectlyInBrowser: false, sourceFile: '', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: false]], pluginFailureResultConstraint: 'FAILURE', profileName: 'jenkins-JenkinsAccessRole-HIPNKMEOC1FL', userMetadata: []

    junit 'reports/*.xml'
  }
}


