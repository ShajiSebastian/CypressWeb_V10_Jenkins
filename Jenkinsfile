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
             sh 'docker run -it -v $PWD:/e2e -w /e2e cypress/included:10.8.0'
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