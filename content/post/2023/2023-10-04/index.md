---
title: AWS Glacier Cleanup
summary: How to delete AWS Glacier vaults.
date: 2023-10-04
categories:
- aws
tags:
- glacier
thumbnail: "images/AmazonWebservices_Logo.png"
---

# Overview

I use [AWS Glacier](https://aws.amazon.com/pm/s3-glacier) to backup my [Synology Diskstation DS923+](https://www.synology.com/en-us/products/DS923+). The [Glacier Backup App](https://kb.synology.com/en-nz/DSM/help/GlacierBackup) from Synology makes it easy to backup the NAS. I switched NAS's and was left with a large number of glacier vaults.

The AWS console does not provide an easy way to delete vaults.

## AWS Glacier FAQ
- [Delete an Archive from a Vault in S3 Glacier](https://docs.aws.amazon.com/amazonglacier/latest/dev/getting-started-delete-archive.html)
- [Delete an Archive in S3 Glacier by Using the AWS CLI](https://docs.aws.amazon.com/amazonglacier/latest/dev/getting-started-delete-archive-cli.html) 

## Delete all vaults
My Vaults contain many Archives, 200k+, and it's not feasible to delete them one at a time. I used the AWS CLI and a bash to delete all the vaults.

## pre-requisites
- [AWS Command Line Interface](https://aws.amazon.com/cli)
- [Configure the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)

## Assets
There are lots of example scripts on the web, and I used them to create my script. I've included it here for reference.
[veuncent/aws_glacier_delete_vault](https://gist.github.com/veuncent/ac21ae8131f24d3971a621fac0d95be5)


