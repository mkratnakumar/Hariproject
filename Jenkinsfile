node{
    def customImage //variable to define the built image
   
    stage('Checkout SCM'){
        checkout scm
        }
       
    stage('Docker build'){
        customImage = docker.build("http://192.168.0.106:8081/repository/dockerr/:${env.BUILD_ID}") //build the image in the docker file using the tag as "myImage:build_number"
        }
       
    stage('Docker push'){
            docker.withRegistry('http://192.168.0.106:8081/repository/dockerr/', 'c4e60567-f349-47e0-af84-a2491b0d815c') { //Push the image to private registry
            customImage.push()
            }
        }
}

