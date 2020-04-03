pipeline {
   agent any 
   stages {
      stage('Git-fetch') {
         steps {
            echo 'Fetching from Git'
            git 'https://github.com/dinukakavinda/jenkinsTest.git'
         }
      }
      
      stage('Build'){
          steps{
            echo 'Building the fetched files'
            bat 'Echo.bat'
          }
      }
      
      stage('Test'){
          steps{
            echo 'This is Testing stage'
          }
      }
      
      stage('Parallel Run'){
          parallel{
              stage('Master run'){
                  agent{
                      label 'Master'
                  }
                  steps{
                      echo 'Running master parallel!'
                  }
              }
              
              stage('Worker run'){
                  agent{
                      label 'Worker'
                  }
                  steps{
                      echo 'Running worker parallel'
                  }
              }
          }
      }
   }
   
   
}
