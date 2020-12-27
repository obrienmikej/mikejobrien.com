# Overview
Steps to deploy this static website to S3.

## prerequisites
to build locally my mac, mikejobrien.com is located in ~github/mikejobrien.com

## remove local content
1. run `rm -rf ~/github/mikejobrien.com/public`
1. run `rm -rf ~/github/mikejobrien.com/resources`

## generate new resources
1. run `cd ~/github/mikejobrien.com`
2. run `hugo`

## sync files to S3
1. run `cd ~/github/mikejobrien.com/public`

## verify changes before sync to S3
1. run `aws s3 sync . s3://mikejobrien.com --delete --acl public-read --dryrun`

## commit changes to S3
1. run `aws s3 sync . s3://mikejobrien.com --delete --acl public-read`

## commit changes to github
1. run `rm -rf ~/github/mikejobrien.com/public`
2. run `rm -rf ~/github/mikejobrien.com/resources`
3. commit to master and push commits to the origin remote

## sitemap
1. Submit sitemap to Google using the Search Console [Sitemaps tool](https://search.google.com/search-console/sitemaps)
2. click add/test sitemap
3. enter `sitemap.xml`

## recrawl
1. Ask Google to recrawl your URLs [google crawl](https://search.google.com/search-console)
2. fetch and render for desktop & smartphone

## upgrade hugo version
What changed [hugo releases](https://github.com/gohugoio/hugo/releases)
1. Run `hugo version`
2. Run `brew upgrade hugo`
3. Run `hugo version`
4. Republish content by repeating all steps above
