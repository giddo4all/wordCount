pipeline {
  agent { label 'linux' }
    stages {
      stage('Test') {
        steps {
          checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
                    doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], 
                    userRemoteConfigs: 
                    [[credentialsId: 'gitHubCreds', url: 'https://github.com/gideonaina/wordCount.git']]])
          sh returnStdout: true, script: 'cd wordCount && sudo ./gradlew --refresh-dependencies && sudo ./gradlew test'
        }
      }
    }
}
