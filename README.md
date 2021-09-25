<div align="center">HashiCorp Packer Practice</div>

I'm learning to build custom machine images using Packer as part of the SheCodeAfrica Cloud School Program.

I'm using tutorials from [Packer's official website](https://learn.hashicorp.com/collections/packer/aws-get-started) and building images for AWS.

**Pre-Requisite**

[Install Packer](https://www.packer.io/downloads)

**1. Build an Image**

I built a t2.micro Amazon EC2 AMI using the Packer template contained in the _aws-ubuntu.pkr.hcl_ file.

In order to authenticate to AWS, inside my AWS console I navigated to _My Security Credentials._ Under _Access keys (access key ID and secret access key)_ I created a new access key.

![](/images/securityCredentials.png)

![](/images/accessKey.png)

To add my AWS credentials as two environment variables, back in my terminal I ran

```
export AWS_ACCESS_KEY_ID=MY_ACCESS_KEY
export AWS_SECRET_ACCESS_KEY=MY_SECRET_KEY
```

To initialize my Packer configuration I ran

```
packer init .
```

Then to format and validate the Packer template I ran the following commands

```
packer fmt .
packer validate .
```

Lastly to build the image I ran _packer build_ followed by the name of the template

```
packer build aws-ubuntu.pkr.hcl
```

![](/images/packerBuild.png)

I then opened my AWS AMI page to verify that Packer had successfully built the AMI.

![](/images/AMI1.png)
