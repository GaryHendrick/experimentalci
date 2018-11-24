// This Jenkinsfile is just for experimentation

def callme()
{
    echo 'callme'
}
node {
    stage('FunctionCall') {
        callme()
    }

    stage('Iteration') {
            for (i in (0..10)) {
                echo "${i}"
            }
    }
}