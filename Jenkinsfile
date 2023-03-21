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
       stage('Running scripts') {
           steps {
               sh 'npx cypress run'
           }
       }
       stage('Deploy') {
           steps {
               echo 'Deploying....'
           }
       }
   }
}