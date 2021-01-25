// Jenkins Declarative Pipeline

pipeline
{
    agent any

    // Optional environment section

    // Optional options section

    // Optional parameters section

    // Optional tools section

    // Optional triggers section

    stages
    {
        stage('Prepare')
        {
            steps
            {
                echo "Preparing the job"
                bat "gnumake -v"
		bat "gnumake version"
            }
        }
        stage('Build')
        {
            steps
            {
                echo "Building"
		bat "gnumake clean build"
            }
        }
        stage('Analyse')
        {
            steps
            {
                echo "Analysis"
		bat "gnumake analyse"
            }
        }
        stage('Test on Host')
        {
            steps
            {
                echo "Hosted testing"
		bat "gnumake hosttest"
            }
        }
        stage('Test on Target')
        {
            steps
            {
                echo "On target testing"
		bat "gnumake targettest"
            }
        }
        stage('Package')
        {
            steps
            {
                echo "Packaging"
		bat "gnumake package"
            }
        }
        stage('Publish')
        {
            when
	    {
                branch "master"
            }

            steps
            {
                echo "Publishing"
		bat "gnumake publish"
            }
        }
    }
    
    post
    {
        always 
        {
            script
            {
                echo "Done"
            }
        }
    }
}
