Deploy site to S3

#remove local content
rm -rf /Users/mike/hugo/mikejobrien.com/public

#generate new content
cd /Users/mike/hugo/mikejobrien.com
hugo

#sync files to S3
cd /Users/mike/hugo/mikejobrien.com/public
#dry run
aws s3 sync . s3://mikejobrien.com --delete --acl public-read --dryrun
#commit
aws s3 sync . s3://mikejobrien.com --delete --acl public-read

#sitemap
Submit it to Google using the Search Console Sitemaps tool
https://www.google.com/webmasters/tools/sitemap-list
-add/test sitemap
#recrawl
Ask Google to recrawl your URLs
https://www.google.com/webmasters/tools/googlebot-fetch
- fetch and render for desktop & smartphone
- request indexing
