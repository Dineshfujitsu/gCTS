@Library('piper-lib-os') _

node() {
  stage('Deploy') {
    gctsDeploy(
      script: this,
      host: 'http://sap-linux.uw3eayeimf1uvkax5xugm5s5da.rx.internal.cloudapp.net:8002',	
      client: '100',
      abapCredentialsId: 'ABAPUserPasswordCredentialsId',
      repository: 'dineshfujitsu-gcts',
      remoteRepositoryURL: 'https://github.com/Dineshfujitsu/gCTS.git',
      role: 'TARGET',
      vSID: 'S4D',
      configuration: [VCS_AUTOMATIC_PULL: 'FALSE',VCS_AUTOMATIC_PUSH: 'FALSE',CLIENT_VCS_LOGLVL: 'debug']
    )
  }
  
  stage('Unit Tests') {
    gctsExecuteABAPUnitTests(
      script: this,
      host: 'https://sap-linux.uw3eayeimf1uvkax5xugm5s5da.rx.internal.cloudapp.net:8002',
      client: '100',
      abapCredentialsId: 'ABAPUserPasswordCredentialsId',
      repository: 'dineshfujitsu-gctsrepo',
    )
  }     
}
