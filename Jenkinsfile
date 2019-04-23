pipeline
{
  agent { label 'hema' }
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
        sh label: '', script: 'SonarQube.Scanner.MSBuild.exe begin /k:"VTfreshers_h_sonar" /d:sonar.organization="vtfreshers-github" /d:sonar.cfamily.build-wrapper-output=bw-output /d:sonar.host.url="https://sonarcloud.io" /d:sonar.login="19117eaedc772a060d1203e22304b82781f5758d"'
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
