node(){
    stage('Preparation') {
        checkout scm
    }
    //stage('Docker build/push') {
         //withEnv(["PATH+cygwin=C:/cygwin/bin:$PATH"]){
      //      docker.withRegistry('https://index.docker.io/v1/', 'docker-hub') {
        //        def dockerfile = 'Dockerfile_java'
          //      def app = docker.build("sushantbhatnagar/dockerized_quandoo", "-f ${dockerfile} .")
            //    app.push('test_0.2')
            //}
         //}
    //}
    stage('Container Tests') {
            //withEnv(["PATH+cygwin=C:/cygwin/bin:$PATH"]){
                def myTestContainer = docker.image('sushantbhatnagar/dockerized_quandoo:latest')
                myTestContainer.pull()
                myTestContainer.inside() {
                // no  java or no jenkins islie fail ho raha hai!
                // withDockerContainer('myTestContainer') {
                   // echo 'inside container'
                    sh("gem install bundler && bundle && bundle exec cucumber -p secure_area features BROWSER=chrome")
                    //echo 'Tests Completed!!'
                //}
           // }
         }
      }
}
