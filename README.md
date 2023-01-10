# Django CD Github Actions

Deploy Django on ECS with Github Actions

## some useful commands

* build and run docker image locally

`docker build -t django_app .`
`docker run -d -p 80:80 django_app`

* IAM user
```
## get current IAM user
aws iam get-user

## get current region
aws configure get region
```

* ECR
```
## list you repos
aws ecr describe-repositories

## authenticate your local Docker daemon against ECR
$(aws ecr get-login --registry-ids <your registry ID> --no-include-email)

## create a repo on ECR
aws ecr create-repository --repository-name <repo name>

## list images on ECR
aws ecr list-images --repository-name <repo name>

## delete image on registry
aws ecr batch-delete-image --repository-name <repo name> --image-ids imageDigest=<the image digest>

## delete repo
aws ecr delete-repository --repository-name <repo name>
```

* ECS
```
## generate a skeleton template for the task definition
aws ecs register-task-definition --generate-cli-skeleton

```
