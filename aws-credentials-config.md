## Aws Credentials

**Description**

> Configure credentials for Aws Cli on local machine
>
> Specs:
>
> * Ubuntu 16.04
> * Aws-cli: 1.11.13
> * Python 3.5

**Config**

```
# vi ~/.aws/credentials
# -----------------------------

[default]
aws_access_key_id = your_aws_access_key
aws_secret_access_key = your_aws_secret_key 
region = us-west-1

[customer_config]
aws_access_key_id=your_aws_access_key
aws_secret_access_key=your_aws_secret_key
```



