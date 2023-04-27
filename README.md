# Follow below steps to create s3 and add these files on the repo to s3
1.Create an S3 bucket:
Login to your AWS account, navigate to the S3 service and create a new bucket with a unique name. Choose the region where you want to host your website.

2.Enable Static Website Hosting:
Select the bucket and click on the "Properties" tab, then click on the "Static website hosting" option. Choose "Use this bucket to host a website" and enter the default page and error page (if any).

3.Set Bucket Permissions:
Click on the "Permissions" tab and scroll down to the "Bucket policy" section. Create a policy that allows public access to your bucket.
Bucket policy :
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::bucket_name/*"
        }
    ]
}

4.Upload Website Files:
Upload your website files to the bucket using the "Upload" button or a third-party tool like Cyberduck or S3cmd.

5.Configure Website URL:
Once the files are uploaded, you need to configure the website URL. Click on the "Static website hosting" option and note down the endpoint URL provided.

6.Update DNS Records:
Finally, update your DNS records to point to the S3 endpoint URL. This can be done by creating a CNAME record or an Alias record in your domain provider's settings.

That's it! Your website is now live and accessible via the URL you specified.

The website with s3 static hosting is for this repo is :
http://static-website-buckets.s3-website-us-east-1.amazonaws.com
