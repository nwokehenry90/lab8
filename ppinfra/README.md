# Lab8 Infrastructure

Pulumi TypeScript project for deploying a static website to AWS.

## Infrastructure Components
- **S3 Bucket**: Hosts static website files
- **CloudFront Distribution**: CDN for global content delivery
- **Synced Folder**: Automatically syncs local files to S3

## Configuration
Edit `Pulumi.dev.yaml` to customize:
- AWS region
- Index document (default: index.html)
- Error document (default: error.html)
- Website content path (default: ./www)

## Deployment
```bash
npm install
pulumi up
```

## Outputs
After deployment, you'll get:
- S3 website URL
- CloudFront CDN URL (recommended for production)
