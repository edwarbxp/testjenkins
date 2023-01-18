pipeline{

  agent any

  stages {
     
    stage('Hello world')
    {
      steps
      {
        echo "$GIT_BRANCH"
      }
    } 
    
    stage('Docker Build')
    {
      steps
      {
        sh(script: 'docker images -a')
        sh(script: """
            cd azure-vote/
            docker images -a
            docker build -t jenkins-pipeline .
            docker images -a
            cd ..
        """)
      }
    } 
  } 
}
