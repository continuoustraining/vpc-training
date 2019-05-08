### Getting started
This simple projects aims to be used as a VPC introduction, from a simple VPC creation to advanced rooting and peering between differents VPCs.
### A cloud formation stack needs to be packaged before being deployed
```
aws --profile schumacher-cloudformation \                                                                                    master 0658fc9
          cloudformation package \
                --template-file vpc.yml \ #root template
                --s3-bucket raphael-cphp \ #s3 bucket dns name
                --s3-prefix bepark \ #folder in s3 bucket
                --output-template-file vpc.template #template file wanted
```
### Then it must be deployed
```
aws cloudformation deploy \
--template-file ./vpc.template \
--stack-name vpc \
--profile schumacher-cloudformation
```

Don't forget to set Ec2KeyPairName parameter in order to not use the default one I used.
