### RDS Aurora Serverless V2
CloudFormation template for creating a stack with Aurora Serverless V2 cluster and instance.

It creates a VPC (Virtual Private Cloud) which is required by the AWS RDS Service. Then, it adds other configurations like Internet Gateway to access the VPC from outside. Finally, it creates the Aurora MySQL Serverless database with the given name and password.

Configuration:
- Allow external connections (outside the VPC).
- DB Encryption enabled.
- DB Cluster + DB Instance.
- Serverless

To run the script for deploying a new CloudFormation stack, you need to install the [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html#getting-started-install-instructions) and set it up with your credentials.

#### Steps
1. Update the `parameters.json` file with the desired username and password.

2. Run the following script, replacing the `stack-name-goes-here` with the correct stack name.
```sh
aws cloudformation deploy --template aurora-serverless-v2-cf.yaml --stack-name stack-name-goes-here --parameter-overrides file://parameters.json
```

3. After running the given script, you should see the creation of the stack in the [CloudFormation](https://console.aws.amazon.com/cloudformation) service.
