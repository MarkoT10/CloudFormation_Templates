# CloudFormation templates to deploy an EC2 instance with the latest Ubuntu image

## Primary CF for creating an AWS Lambda together with an IAM Role.

Primary CloudFormation template is for creating an IAM role for a Lambda function as well as the Lambda function itself. The IAM role is called EC2ReadOnlyAccessRole and has a policy that allows the Lambda function to describe EC2 images. The Lambda function is called LatestAmiLambdaFunction and retrieves the latest Amazon Machine Image (AMI) id that matches certain criteria.

## Secondary CF template is for creating an EC2 and also imports the latest AMI.

Secondary CloudFormation template links to the first template and imports the latest AMI id as a variable, this CF template creates an EC2 instance and uses the imported AMI id as the image for the instance. This EC2 instance also has a security group that allows incoming SSH traffic and the template also exports the latest AMI id as an output.
