pipeline
{
  agent { hema }
  stages
  {
    stage ('fetch_code')
    {
      steps
      {
        git 'https://github.com/VTfreshers/h_sonar'
      }
    }
    stage ('code_analyse')
    {
      steps
      {
        sh label: '', script: '''sonar-scanner \\
            -Dsonar.projectKey=VTfreshers_h_sonar \\
            -Dsonar.organization=vtfreshers-github \\
            -Dsonar.sources=. \\
            -Dsonar.cfamily.build-wrapper-output=bw-output \\
            -Dsonar.host.url=https://sonarcloud.io \\
            -Dsonar.login=3a9026695b1f0e79319ca8724b31f216cd794226'''
      }
    }
    stage ('testing')
    {
      steps
      {
        echo 'fetching and code analysis completed'
        echo 'tesing stage' 
      }
    }
  }
}
