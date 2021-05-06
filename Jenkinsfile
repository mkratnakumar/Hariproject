node{
    def myapp //variable to define the built image
   
    stage('Checkout SCM'){
        checkout scm
        }
       
    stage('Docker Build'){
        myapp = docker.build("192.168.0.106:8083:${env.BUILD_ID}") //build the image in the docker file using the tag as "myImage:build_number"
        }
       
    stage('Docker push'){
            docker.withRegistry('192.168.0.106:8083', 'c4e60567-f349-47e0-af84-a2491b0d815c') { //Push the image to private registry
            myapp.push()
            }
        }
}

