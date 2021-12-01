pipeline {
 agent any
 stages {
  stage('Checkout SCM') {
   steps {
    git 'https://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@github.com/FarinTahrima/JenkinsDependencyCheckTest.git'
   }
  }

  stage('OWASP DependencyCheck') {
   steps {
    dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
   }
  }
 } 
 post {
  success {
   dependencyCheckPublisher pattern: 'dependency-check-report.xml'
  }
 }
}
