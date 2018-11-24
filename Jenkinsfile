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
    stage("scoped_past")
    {
        def scoped_past = "scoped_past"
    }

    // This stage attempts to access a number of variables declared in previous scopes
    stage("scoped_present")
    {
        echo "${filescoped} was declared in the file scope"
        echo "${nodescoped} was declared in the node scope"
        echo "${scoped_past} was declared in the scoped_past"
        echo "${scoped_future} will be declared in scoped_future"
    }

    // This stage provides a location in which you can test the scope of declartions conducted south of present
    stage("scoped_future")
    {
        def scoped_future="scoped_future"
    }
}