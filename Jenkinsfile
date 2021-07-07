@Library('jenkins-helpers') _

void pod(body) {
  dockerUtils.pod() {
    imageVulnerabilityScanner.pod() {
      dockle.pod() {
        node(POD_LABEL) {
          body()
        }
      }
    }
  }
}

pod {
  stage("Checkout from GitHub") {
    checkout(scm)
  }

  stage("Build docker image") {
    buildInfo = dockerUtils.build()
  }

  stage("Dockle scan") {
    dockle.dockleScan("${buildInfo.imageName}:${buildInfo.imageTag}")
  }

  stage("Vulnerability scan") {
    imageVulnerabilityScanner.scan("${buildInfo.imageName}:${buildInfo.imageTag}")
  }

  if (env.BRANCH_NAME == 'main') {
    stage("Push image to GCR") {
      dockerUtils.push(buildInfo.image)
    } 
  }
}