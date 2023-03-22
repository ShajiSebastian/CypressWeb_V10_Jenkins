pipeline {
  agent {
    // this image provides everything needed to run Cypress
    docker {
      image 'cypress/included:10.8.0'
    }
  }


   tools {nodejs "NodeMar2023"}

       environment {
        CHROME_BIN = '/bin/google-chrome'
    }

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
             sh 'docker run -it -v $PWD:/e2e -w /e2e cypress/included:10.8.0'
               
           }
       }
       stage('Deploy') {
           steps {
               echo 'Deploying....'
           }
       }
   }
}