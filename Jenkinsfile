
pipeline {
    agent any

    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['dev', 'qa', 'prod'],
            description: 'Select the target deployment environment'
        )
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout: Simulating source-code checkout for customer-api.'
            }
        }

        stage('Build') {
            steps {
                script {
                    def applicationName = 'customer-api'
                    def targetEnvironment = params.ENVIRONMENT
                    def applicationVersion = '1.0.0'

                    echo "Application Name: ${applicationName}"
                    echo "Environment: ${targetEnvironment}"
                    echo "Application Version: ${applicationVersion}"
                    echo 'Build: Application build simulated successfully.'
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Test: Starting application tests (simulation).'

                script {
                    def environments = ['dev', 'qa', 'prod']

                    environments.each { environmentName ->
                        echo "Processing environment: ${environmentName}"
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    def targetEnvironment = params.ENVIRONMENT

                    if (targetEnvironment == 'dev') {
                        echo 'Development deployment started.'
                    } else if (targetEnvironment == 'qa') {
                        echo 'QA deployment started.'
                    } else if (targetEnvironment == 'prod') {
                        echo 'Production deployment requires approval.'
                        echo ' please give the approval'
                    } else {
                        error("Invalid environment: ${targetEnvironment}")
                    }

                    echo 'Note: Deployment is simulated; no application was deployed.'

                }
            }
        }
    }
}
