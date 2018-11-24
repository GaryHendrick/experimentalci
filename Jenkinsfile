// This Jenkinsfile is just for experimentation

def callme()
{
    echo 'callme'
}

def filescoped = "filescoped" // A variable declared at the file scope.

node {
    def nodescoped = "nodescoped" // A variable declared at the node bolock

    stage('FunctionCall') {
        callme()
    }

    stage('Iteration') {
            for (i in (0..10)) {
                echo "${i}"
            }
    }

    // This stage provides a number one or two declarations which will be accessed later
    stage("past")
    {
        def staged_past = "staged_past"
    }

    // This stage attempts to access a number of variables declared in previous scopes
    stage("present")
    {
        echo "${filescoped} was declared in the file scope"
        echo "${nodescoped} was declared in the node scope"
        try { echo "${scoped_past} was declared in the scoped_past" }
        catch { echo "the staged_past variable is not available within this stage" }
        try { echo "${scoped_future} will be declared in scoped_future" }
        catch { echo "the staged_future variable is not available within this stage" }
    }

    // This stage provides a location in which you can test the scope of declartions conducted south of present
    stage("future")
    {
        def staged_future="staged_future"
    }
}