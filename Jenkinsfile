node {

    stage('SCM') {
        checkout scm
    }

    stage('SonarQube Analysis') {

        def scannerHome = tool 'mySonar'

        withEnv([
            'SONAR_HOST_URL=http://34.204.13.203:9000/',
            'SONAR_TOKEN=sqa_4d55cb8e391f0fed55c794d4820bcf743aaacdb9'
        ]) {

            sh """
            ${scannerHome}/bin/sonar-scanner \
            -Dsonar.projectKey=Pyhelloworld \
            -Dsonar.projectName=Pyhelloworld \
            -Dsonar.sources=. \
            -Dsonar.host.url=$SONAR_HOST_URL \
            -Dsonar.token=$SONAR_TOKEN
            """
        }
    }
}
