# CDKTF Convert

This repo is a simple example of how to convert existing HCL configurations into a CDKTF equivalent.

## Demo Scenario

In this demo, the Terraform run is local, and deploy an nginx container on a local docker engine.

## How to use it

### Testing the HCL code

Run these commands:

```HCL
terraform init
terraform apply -auto-approve
```

Once you have verified that nginx is running on http://localhost:8000, you can clean up the environment, with this command: 

```HCL
terraform destroy -auto-approve
```

### Generating and testing the CDKTF code

Run these commands:

```BASH
mkdir -p converted/typescript
cd converted/typescript
cdktf init --from-terraform-project ../.. --local
cdktf deploy
```

Once you have verified that nginx is running on [http://localhost:8000](http://localhost:8000), you can clean up the environment, with this command:

```BASH
cdktf destroy -auto-approve
```
