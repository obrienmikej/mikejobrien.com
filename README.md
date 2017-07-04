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
