pipeline {
    agent any
    stages {
        stage ("Clone Code") {
            steps {
                git "$github_url"
            }
        }
        stage ("Build Img") {
            steps {
                sh 'docker build -t $image_name $df_path'
            }
        }
        stage ("Deploy Img") {
            steps {
                sh 'docker run -itd --name $container_name -p $host_port:$container_port $image_name'
            }
        }
    }
}
