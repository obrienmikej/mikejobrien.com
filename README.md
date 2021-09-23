# Overview

- Steps to deploy the mikejobrien.com static website.

## deploy with github-actions

- on commit to master, new content will be deployed using github actions (details in .github/workflows/main.yaml)

## update github-actions hugo version

- update .github/workflows/main.yml and set hugo-version: 'x.xx.x' to version specified on [hugo/releases](https://github.com/gohugoio/hugo/releases)

## local prerequisites

- hugo
- awscli
- git
- brew

## local development

- to build locally on my mac, mikejobrien.com is located in ~github/mikejobrien.com

## start with current hugo version

What changed [hugo releases](https://github.com/gohugoio/hugo/releases)

1. Run `hugo version` #note version before
2. Run `brew upgrade hugo`
3. Run `hugo version` #note version after

## clone source locallay

1. Run `cd ~/github`
1. Run `git clone <https://github.com/obrienmikej/mikejobrien.com.git>`

## generate new resources after new content added (pages, images..)

1. run `cd ~/github/mikejobrien.com`
2. run `hugo`

## verify changes using hugo deploy to push files to S3 and invalidate cdn

1. run `hugo deploy -dryRun`

## commit changes using hugo deploy to push files to S3 and invalidate cdn

1. run `hugo deploy`

## commit changes to github

1. run `rm -rf ~/github/mikejobrien.com/public`
2. commit to master and push commits to the origin remote

## sitemap

1. Submit sitemap to Google using the Search Console [Sitemaps tool](https://search.google.com/search-console/sitemaps)
2. click add/test sitemap
3. enter `sitemap.xml`

## recrawl

1. Ask Google to recrawl your URLs [google crawl](https://search.google.com/search-console)
2. fetch and render for desktop & smartphone

## backup step to manually sync files to s3 locally

## sync files to S3

1. run `cd ~/github/mikejobrien.com/public`

## verify changes before sync to S3

1. run `aws s3 sync . s3://mikejobrien.com --delete --acl public-read --dryrun`

## commit changes to S3

1. run `aws s3 sync . s3://mikejobrien.com --delete --acl public-read`
