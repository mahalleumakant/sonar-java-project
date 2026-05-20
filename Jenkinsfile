node {

    stage('SCM') {
        checkout scm
    }

    stage('SonarQube Analysis') {

        def scannerHome = tool 'mySonar'

        withEnv([
            'SONAR_HOST_URL=http://54.237.245.52:9000',
            'SONAR_TOKEN=sqa_560dd47b07cde50e010734d065f7a193ddadc43a'
        ]) {

            sh """
            ${scannerHome}/bin/sonar-scanner \
            -Dsonar.projectKey=python \
            -Dsonar.projectName=python \
            -Dsonar.sources=. \
            -Dsonar.host.url=$SONAR_HOST_URL \
            -Dsonar.token=$SONAR_TOKEN
            """
        }
    }
}
