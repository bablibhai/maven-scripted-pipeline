node ("Devops-node"){
    def mvn_version = 'maven3.8.4'

    stage('clone') { // for display purposes
        git 'https://github.com/bablibhai/java-web-app-docker.git'
    }
    stage('Build') {

            if (isUnix()) {
                    withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
                    sh '"mvn" -Dmaven.test.failure.ignore clean package'
                    }
                
            } else {
                bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
            }
    }
}
