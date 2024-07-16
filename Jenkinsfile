pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/Raven988/OWASP-Dependency-Check.git'
            }
        }
        stage('DependencyCheck') {
            steps {
                dependencyCheck additionalArguments: '''--format HTML
--enableExperimental''', odcInstallation: 'DP-Check-10.0'
            }
        }
    }
}
