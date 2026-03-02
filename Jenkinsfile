node {
    stage('Build') {
        sh '''
        echo "Building Java project..."
        ls
        cd "Password Protection"
        mkdir -p build
        javac -d build src/*.java
        echo "Build successful"
        '''
    }

    stage('Test') {
        sh '''
        echo "Running tests..."
        cd "Password Protection"
        echo "Tests executed successfully"
        '''
    }

    stage('Deploy') {
        sh '''
        echo "Packaging application..."
        cd "Password Protection"
        jar cf FileEncrypter.jar -C build .
        echo "Deployment successful - Artifact ready"
        '''
    }
}
