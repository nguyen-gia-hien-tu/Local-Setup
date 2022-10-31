## This documentation goes through installation of AWS CLI and some tips related to it

## AWS CLI
To install AWS CLI, follow [Installing or updating the latest version of the AWS
CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
or using the following command:

```zsh
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

# Clean up
rm -rf aws awscliv2.zip
```


## Tips
### Tip 1
To delete all untagged image in an AWS ECR repository, do the following:

```zsh
# This requires jq installed
# Use `sudo apt install jq` to install it
aws ecr describe-images --repository-name oneai-dda-liveops-deployment_test/custom_workbench --filter tagStatus=UNTAGGED | jq ".imageDetails[].imageDigest" | xargs -I {} aws ecr batch-delete-image --repository-name oneai-dda-liveops-deployment_test/custom_workbench --image-ids imageDigest={}
```
