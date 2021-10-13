# summary
- We will create a machine on EC2. 
  From our local machine, we will connect to this new EC2 machine via ssh.
  This EC2 machine will act as a controller to run our tests. 

# pre-requests
- aws credentials
- aws machine access over ssh, each aws region needs to know your ssh keys
  - see the keys by changing region with this url: https://us-east-2.console.aws.amazon.com/ec2/v2/home?region=us-east-2#KeyPairs:search=jen
- aws cli v1 installed on your aws machine
  - curl "https://s3.amazonaws.com/aws-cli/awscli-bundle-1.19.101.zip" -o "awscliv1.zip"
- install git
- install java 8 or newer one
- port 61616 must be available for tcp connection
- port 22 must be available for ssh connection

# installation
- clone https://github.com/ahmetmircik/wan-demo.git
- run `./wan-demo/install`

# tests
- have HAZELCAST_EE_KEY environment variable in your ~/.bashrc
- clone https://github.com/ahmetmircik/wan-demo-scenarios
- enter a test directory
- open `go` script with `vi go` then edit lines starting with `aws-create` to use your ssh keys
  - `aws-create --key your-ssh-key ...`
  - for multi-region tests your ssh key must be available in each region 
- run `./go 5.0`



