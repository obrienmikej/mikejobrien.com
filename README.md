# Overview
Steps to deploy static website to S3.

## remove local content
1. run `rm -rf /Users/mike/hugo/mikejobrien.com/public`

## generate new content
1. run `cd /Users/mike/hugo/mikejobrien.com`
2. run `hugo`

## sync files to S3
1. run `cd /Users/mike/hugo/mikejobrien.com/public`

## verify changes before sync to S3
1. run `aws s3 sync . s3://mikejobrien.com --delete --acl public-read --dryrun`

## commit
1. aws s3 sync . s3://mikejobrien.com --delete --acl public-read

## sitemap
1. Submit sitemap to Google using the Search Console [Sitemaps tool](https://www.google.com/webmasters/tools/sitemap-list)
2. click add/test sitemap

## recrawl
1. Ask Google to recrawl your URLs [google crawl](https://www.google.com/webmasters/tools/googlebot-fetch)
2. fetch and render for desktop & smartphone
3. request indexing
