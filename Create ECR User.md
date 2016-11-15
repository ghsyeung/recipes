
```
aws iam create-user --user-name=ecr_user
aws iam create-access-key --user-name=ecr_user
```

Add the user credentials to `.aws/credentails`

```
aws iam attach-user-policy --user-name="perked_ecr" --policy-arn="arn:aws:iam::aws:policy/AmazonEC2ContainerRegistryPowerUser"
```

Wait for a few minutes for policy to propagate, then check with

```
aws --profile=ecr_user ecr get-login
```

