pipeline {
    agent any
    pipeline {
    agent any
    tools {
        jdk 'jdk21'
    }
    environment {
        SCANNER_HOME = tool 'sonar-scanner'
    }
}
  

    stages {
        stage('Git checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/keerthana2-005/CI_CD.git'
            }
        }
    }
    stage("Sonarqube Analysis "){
            steps{
                        bat  """
                            ${SCANNER_HOME}/bin/sonar-scanner \
                            -Dsonar.projectName=CI_CD \
                            -Dsonar.host.url=http://localhost:9000 \
                            -Dsonar.login=squ_9cf226241d6d15cbe75fb6b40fed633e6b7c78d7\
                            -Dsonar.java.binaries=. \
                            -Dsonar.projectKey=CI_CD """
            }
        }

}
