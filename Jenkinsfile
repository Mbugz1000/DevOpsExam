node {

stage('Clone Repository')
{
checkout scm
}

stage('Build docker image'){

sh "docker build -t devopsexam:latest ."
}

stage('Docker login to hub and push the image'){
sh "docker login -u 'mbugz1000' -p 'MbugzT@yahoo' "
sh "docker tag devopsexam:latest  mbugz1000/devopsexam:latest"
sh "docker push mbugz1000/devopsexam:latest"
}

stage('Docker run the Image'){
sh "docker container run --detach --publish 80:7120 --name simplesite mbugz1000/devopsexam:latest" 	
}

}