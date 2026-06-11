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

## Challenges Encountered

During deployment, I encountered and resolved several common AWS configuration issues, including:

- S3 bucket permission errors
- CloudFront origin configuration issues
- AccessDenied errors caused by incorrect endpoint selection
- Static website hosting configuration validation

Troubleshooting these issues helped me better understand how S3 permissions and CloudFront origins interact.

## Lessons Learned

Through this project, I gained experience with:

- AWS cloud fundamentals
- Static website hosting
- CloudFront content delivery networks (CDNs)
- S3 bucket policies and permissions
- HTTPS website delivery
- Git and GitHub workflows
- Cloud architecture concepts

## Future Improvements

Potential enhancements include:

- Custom domain registration
- Route 53 DNS configuration
- AWS Certificate Manager (ACM) integration
- Automated deployments using GitHub Actions
