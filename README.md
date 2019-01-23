# Phanindra_challenge


Architecting a scalable and secure static web application in AWS and Creating and deploying the static website through Ansible configuration management tool 

1. Create a S3 bucket in AWS console

Choose Create bucket.
In the Bucket name field, type a unique DNS-compliant name for your new bucket. ...
For Region, choose the region where you want the bucket to reside.
Choose Create

2. Configuring the S3 Bucket for Static Website Hosting

Navigate to S3 in the AWS Console.
Click into your bucket.
Click the “Properties” section.
Click the “Static website hosting” option.
Select “Use this bucket to host a website”.

--- By default, any new buckets created in an AWS account deny the ability to add a public access bucket policy, for our use case, we need a public access bucket policy. 

Click into your bucket.
Select the “Permissions” tab at the top.
Under “Public Access Settings” we want to click “Edit”.
Change “Block new public bucket policies” to be false and Save.

-- The steps to update the policy of your bucket in the AWS Console are as follows:

Navigate to S3 in the AWS Console.
Click into your bucket.
Click the “Permissions” section.
Select “Bucket Policy”.
Add the following Bucket Policy and then Save
{
    "Version": "2008-10-17",
    "Id": "PolicyForPublicWebsiteContent",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::www.my-site.com/*"
        }
    ]
}

3. Uploading Your Static Website 

-- Upload static website to S3 via the AWS Console by completing these steps:

Navigate to S3 in the AWS Console.
Click into your bucket.
Click the “Upload” button.
Drag and drop or select “Add files”, and add the entire static website directory.
Click “Next”.
Leave the default permissions S3 offers.
Click “Next”.
Leave the default permissions for “Set properties”.
Click “Next”.
Click “Upload”.
