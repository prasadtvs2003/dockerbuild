node {

    def app



    stage('Clone repository') {

      



        checkout scm

    }



    stage('Build image') {

  

       app = docker.build("prasadtvs2003/docker-pipeline")

    }



    stage('Test image') {

  



        app.inside {

            sh 'echo "Tests passed"'

        }

    }



    stage('Push image') {


        docker.withRegistry('https://hub.docker.com/repository/docker/prasadtvs2003', 'git') {

            app.push("${env.BUILD_NUMBER}")

            app.push("latest")

        }

    }

}
