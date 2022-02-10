pipeline {
  agent any 
  tools {
    maven 'Maven'
  }
  stages {
    stage ('Initialize') {
      steps {
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}" 
      }
    }
    
   /* stage ('Check-Git-Secrets') {
      steps {
        sh 'rm trufflehog || true'
        sh 'docker run gesellix/trufflehog --json https://github.com/swethabunari/webpipeline.git > trufflehog'
        sh 'cat trufflehogg'
      }
    }
    
    stage ('Source Composition Analysis') {
      steps {
         sh 'rm owasp* || true'
         sh 'wget "https://raw.githubusercontent.com/cehkunal/webapp/master/owasp-dependency-check.sh" '
         sh 'chmod +x owasp-dependency-check.sh'
         sh 'bash owasp-dependency-check.sh'
         sh 'cat /var/lib/jenkins/OWASP-Dependency-Check/reports/dependency-check-report.xml'
        }
      }*/
    
    
    stage ('Container Scan') {
       steps {
         sh 'docker run aquasec/trivy:0.18.3 vulnerables/phpldapadmin-remote-dump'
             }
         }
}
}    
