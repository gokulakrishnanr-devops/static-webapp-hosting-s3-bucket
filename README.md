# static-webapp-hosting-s3-bucket
How to host a static website in 5 mins

Static Website Hosting using Amazon S3

Project Overview

This project demonstrates how to host a static website using Amazon S3 (Simple Storage Service). The implementation includes bucket creation, configuration of static website hosting, generation and application of a public bucket policy, and verification of the deployed website.

Architecture

Client Browser
→ S3 Static Website Endpoint
→ Publicly Accessible S3 Bucket
→ Static Files (HTML, CSS, JS)

Prerequisites

AWS Account
IAM user with S3 permissions
Static website files (e.g., index.html, CSS, JS assets)

Step 1: Create an S3 Bucket
Open AWS Console.
Navigate to S3.
Click Create Bucket.
Provide a globally unique bucket name.
Uncheck Block all public access.
Create the bucket.
Upload your static website files into the bucket.

Step 2: Enable Static Website Hosting
Open the created bucket.
Navigate to Properties.
Enable Static Website Hosting.
Specify:
  Index document: index.html
  Error document: (optional)

Step 3: Generate Bucket Policy

Open S3 Policy Generator in a new tab.
Select policy type: S3 Bucket Policy.
Configure:
  Effect: Allow
  Principal: *
  Action: s3:GetObject
  ARN: arn:aws:s3:::your-bucket-name/*
Generate policy.

Step 4: Apply Bucket Policy
Go to bucket → Permissions.
Open Bucket Policy.
Paste generated JSON policy.
Ensure resource ends with:
  "Resource": "arn:aws:s3:::your-bucket-name/*"

Sample policy structure
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Statement1",
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:GetObject"
      ],
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }

  Step 5: Access the Website

Go to Objects.
Select index.html.
Copy the Object URL.
Paste it into browser (preferably Incognito mode).
  ]
}
