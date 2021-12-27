# aws_EC2_SSM


create IAM Role

Common use cases as EC2 
 
select a service to view its use cases as EC2

then select use case as

EC2 Role for AWS Systems Manager

create the role.

select the role you have  created
and attach polcies.
create new policy and add the json text edit and paste the below content.

{ 
  "Version": "2012-10-17", 
  "Statement": [ 
    { 
      "Effect": "Allow", 
      "Action": [ 
      "ssm:PutParameter" 
      ], 
      "Resource": [ 
        "arn:aws:ssm:*:*:parameter/EC2Rescue/Passwords/i-*" 
        ] 
    } 
  ] 
}
attach the policy to your ec2 instance which one you want to recover password.


2.    Open the AWS Systems Manager console, and then choose Run Command from the navigation pane.

3.    Choose Run a Command.

4.    For Command document, choose AWSSupport-RunEC2RescueForWindowsTool.

5.    For Command parameters, verify that Command is set to ResetAccess.

6.    For Targets, choose Choose instances manually, and then select your instance.

7.    Choose Run.

8.    In the Targets and outputs section, select the Instance ID for your instance.

9.    Choose View output for instructions on how to retrieve the new password.

10.    After you regain access to your instance, it’s a best practice to rotate the password and then delete the parameter from Parameter Store.
