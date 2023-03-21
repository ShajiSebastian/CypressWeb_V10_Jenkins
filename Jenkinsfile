pipeline {
   agent any

   tools {nodejs "NodeMar2023"}

   stages {
       stage('Dependencies') {
           steps {
               sh 'npm i'
               sh 'npm install lambdatest-cypress-cli'
           }
       }
       stage('e2e Tests') {
           steps {
               sh 'npm run runAllTestsInBackground'
           }
       }
       stage('Deploy') {
           steps {
               echo 'Deploying....'
           }
       }
   }
}