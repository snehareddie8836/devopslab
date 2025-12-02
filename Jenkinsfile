pipeline{
agent any

stages{
stage("Clone Repository") {
steps {
git url: "https://github.com/snehareddie8836/cnslab.git', branch: 'main'
}
}

stage('Build Docker Image') {
steps{
bat'docker build -t reg:v1 .'
}
}

stage('Run Docker Container') {
steps{
bat 'docker rm -f reg-container || exit 0'
bat 'docker run -d -p 5000:5000 --name reg-container reg:v1'
}
}
}

}
