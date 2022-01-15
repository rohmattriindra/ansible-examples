## Requirements
pip3 install -r requirements.txt


## How to
```bash
aws configure set --profile awsdev aws_access_key_id access_key
```
```bash
aws configure set --profile awsdev aws_secret_access_key access_secret
```
```bash
aws configure set --profile awsdev region ap-southeast-1
```

```bash
AWS_PROFILE=awsdev ansible-playbook -i inventory/preproduction/ playbook/create-vpc.yaml -v
```
