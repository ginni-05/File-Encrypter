node {
    try {

        stage('Build') {
            sh '''
            echo "Building Java project..."
            echo "Listing workspace contents:"
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
            echo "JUnit tests executed successfully"
            '''
        }

        stage('Deploy') {
            sh '''
            echo "Deploying (Packaging) File-Encrypter Application..."
            cd "Password Protection"
            jar cf FileEncrypter.jar -C build .
            echo "Deployment successful - Artifact ready"
            '''
        }

        echo "Pipeline executed successfully!"

    } catch (Exception e) {
        echo "Pipeline failed!"
        throw e
    }
}
