node{
    def myapp //variable to define the built image
   
    stage('Checkout SCM'){
        checkout scm
        }
       
    stage('Docker build'){
        myapp = docker.build("192.168.0.105:8083/app:${env.BUILD_ID}") //build the image in the docker file using the tag as "myImage:build_number"
        }
       
    stage('Docker push'){
            docker.withRegistry('192.168.0.105:8083', '2bfcee9b-32d5-4dfc-81f0-615448b0c1f3') { //Push the image to private registry
            myapp.push()
            }
        }
}

