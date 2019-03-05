pipeline {
  agent any
 
  options {
    copyArtifactPermission(projectNames: 'horizon*')
  }

  stages {
    stage('package') {
      steps {
        dir('dist') {
          deleteDir()
        }
        sh 'python setup.py sdist'
        sh 'find dist -type f -exec cp {} dist/django_openstack_auth.tar.gz \\;'
        archiveArtifacts(artifacts: 'dist/django_openstack_auth.tar.gz', onlyIfSuccessful: true)
      }
    }
  }
}
