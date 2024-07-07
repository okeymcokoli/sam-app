# sam-app
Using AWS Serverless Application Model (SAM) to deploy a microservice

This repository shows how to utilize SAM-CLI to deploy a simple Serverless Application using Lambda and REST API. The project be verified for proper functionality using:
1. The API Endpoint url and 
2. Docker runner on localhost.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](getting-started)
- [Start Deployment](#start-deployments)
- [Endpoints](#endpoints)
- [API-Endpoint-Invoke Lambda](#API-Endpoint-Invoke-Lambda)
- [Docker-Invoke Lambda](#Docker-Invoke-Lambda)
- [Contributing](#contributing)
- [License](#license)

### Prerequisites - reference AWS documentations to install and configure your CLI

- Install AWS CLI - https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
- Configure AWS CLI - https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html
- Install SAM - https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html#install-sam-cli-instructions
- Install Docker - https://docs.docker.com/get-docker/


Verify your installations by running these commands:

1. 

```
   aws
```

2. 

```
sam
```

3. 

```
docker --version
```
You should get custom feedbacks showing successful and functional installations for aws and sam.

- Create an IAM user with permissions to deploy Lambda and REST API (For tutorial purposes only, you can assign Admin access to your IAM). run the following cmd and follow the prompt to configure your iam-user using the cli.

4. 

```
aws configure
```

### Getting Started

1. Clone the repository:
   git clone https://github.com/okeymcokoli/sam-app.git

2. cd sam-app and ensure all the file parameters and update variable match your desired resource name and region (you can use template as provided or update if you desire). 


### Start Deployments
1. Once your variables are in place, run the following cmd on your CLI

    ```
    sam build
    ```

2. The "build is successful" displayed on the terminal shows you it is time to deploy, run:
    ```
    sam deploy --guided
    ```
3. Answer prompt questions and enter 'y' to confirm answers and initiate deploy.

4. Review the CloudFormation stack changeset and enter 'Y'[YES] to confirm resources to be deployed.

    - [ ] AWS Lambda Permission
    - [ ] AWS IAM Role
    - [ ] AWS Lambda Function
    - [ ] AWS API Gateway
    - [ ] AWS API stage
    - [ ] AWS REST API

5. Verify your resources have been successfully deployed using the Endpoints.

### Endpoints

1. Use your API Endpoint url to return response from your lambda function:

```
https//restapi_id.execute-api.region.amazonaws.com/stage_name/
```

2. Start your application locally using Docker:

```
sam local start-api
```

sam will launch a docker container and provide you with your localhost id and the exposed port.

3. 

```
http://localhost:3000

```


### API-Endpoint-Invoke Lambda
4. copy and paste your API Endpoint with a stringQuery to trigger lambda and return result:

```
https//restapi_id.execute-api.region.amazonaws.com/stage_name/hello?personid=10
```

### Docker-Invoke Lambda
5. copy and paste your localhost id with a stringQuery to trigger lambda and return result:

```
http://localhost:3000/hello?personid=11
```

## Contributing
Contributions are welcome! Feel free to open issues, submit pull requests, or provide suggestions to improve this project.

## License
This project is licensed under the MIT License.
