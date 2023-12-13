node {

   def registryProjet='marc-app/'
   def IMAGE="${registryProjet}app:0.0.7"

    stage('Clone') {
          checkout scm
    }

    def img = stage('Build') {
          docker.build("$IMAGE",  '.')
          }

    stage('Run') {
          img.withRun("--name run-$BUILD_ID") { c ->
       
          }
    }

    stage('Push') {
       docker.withRegistry('https://registry.ludovic.io/' , 'harbormg_id') {
              img.push 'latest'
              img.push()
          }
    }

}

