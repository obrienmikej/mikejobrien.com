# Overview
Steps to deploy this static website to S3.

## prerequisites
mikejobrien.com is located in ~hugo/mikejobrien.com

## remove local content
1. run `rm -rf ~/hugo/mikejobrien.com/public`

## generate new content
1. run `cd ~/hugo/mikejobrien.com`
2. run `hugo`

## sync files to S3
1. run `cd ~/hugo/mikejobrien.com/public`

## verify changes before sync to S3
1. run `aws s3 sync . s3://mikejobrien.com --delete --acl public-read --dryrun`

## commit changes to S3
1. run `aws s3 sync . s3://mikejobrien.com --delete --acl public-read`

## sitemap
1. Submit sitemap to Google using the Search Console [Sitemaps tool](https://www.google.com/webmasters/tools/sitemap-list)
2. click add/test sitemap
3. enter `sitemap.xml`

## recrawl
1. Ask Google to recrawl your URLs [google crawl](https://www.google.com/webmasters/tools/googlebot-fetch?hl=en&siteUrl=https://mikejobrien.com/)
2. fetch and render for desktop & smartphone

## upgrade hugo version
What changed [hugo releases](https://github.com/gohugoio/hugo/releases)
1. Run `hugo version`
2. Run `brew upgrade hugo`
3. Run `hugo version`
4. Republish content by repeating all steps above
