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
            -Dsonar.login=d93216982649e9cabc544ccb4d5302dd9134f6d9'''
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
