# SkyHigh Portfolio Project 1 — Static Website on AWS

My personal portfolio website, deployed on AWS using S3 for storage
and CloudFront for HTTPS + global delivery.

**Live URL:** https://d2lm54mkdej34l.cloudfront.net/

## What I Built
- HTML + CSS portfolio site
- S3 bucket configured for static website hosting
- CloudFront distribution with HTTPS enforced
- Public bucket policy allowing `s3:GetObject`

## What I Learned
- How S3 static website hosting works
- How CloudFront distributes content globally
- How to configure a bucket policy from scratch
- Why HTTPS matters and how CloudFront handles certificates

## Architecture

```text
                 ┌─────────────┐
                 │   User      │
                 │  (Browser)  │
                 └──────┬──────┘
                        │ HTTPS
                        ▼
              ┌──────────────────┐
              │   CloudFront     │
              │      (CDN)       │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │    S3 Bucket     │
              │ Static Website   │
              │ Hosting Enabled  │
              └──────────────────┘



### How It Works

1. A user visits the website using the CloudFront URL.
2. CloudFront serves content over HTTPS.
3. CloudFront retrieves files from the S3 bucket.
4. The S3 bucket stores the website files.
5. CloudFront caches content globally for faster delivery.
