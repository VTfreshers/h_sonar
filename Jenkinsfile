pipeline
{
  agent any
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
  -Dsonar.login=76a68f14c5c54a1726db65c15840e39d14ca44b2'''
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
