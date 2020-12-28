---
title: GitHub-actions for hugo deployments
summary: Setup github-actions workflow for automated hugo s3 deployment
date: 2020-12-26
categories:
- github
tags:
- automation
thumbnail: "images/github-actions.png"
---

# Overview
How I setup github-actions to deploy my hugo site to s3 on commit to main. I was already running my site on S3 using hugo with route53, cloudfront cdn and https. This post is specific to automated deployments.

## References
- [Using GitHub Actions and Hugo Deploy to Deploy a Static Site to AWS](https://capgemini.github.io/development/Using-GitHub-Actions-and-Hugo-Deploy-to-Deploy-to-AWS)
- [GitHub Actions for Hugo](https://github.com/peaceiris/actions-hugo)

## High-level details
1. added aws secrets to github
2. setup new limited access in AWS
- added new IAM user "githubcicd" and using access keys on this user
- added new IAM policy "GitHubActionsPolicy", limited access to s3,cloudfront
3. added deployment config in config.toml
- name
- s3 url
- cloudFrontDistributionID
4. added resources required to build in github
- assets/scss
- resources/_gen/assets/sass
5. added file to automate deployment
- .github/workflows/main.yaml
