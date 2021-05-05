pipeline{
    def myapp //variable to define the built image
   
    stage('Checkout SCM'){
        checkout scm
        }
       
    stage('Docker build'){
        myapp = docker.build("myapp:${env.BUILD_ID}") //build the image in the docker file using the tag as "myImage:build_number"
        }
       
    stage('Docker push'){
            docker.withRegistry('http://192.168.0.105:8081', 'd4ad66d0-791c-4ee8-8953-f91deab9fc00') { //Push the image to private registry
            myapp.push()
            }
        }
}

