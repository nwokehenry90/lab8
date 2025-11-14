# GitHub Secrets Setup Guide

Before you can run the GitHub Actions workflows, you need to configure the following secrets in your GitHub repository.

## Required Secrets

### 1. AWS Credentials (Traditional Method)
- `AWS_ACCESS_KEY_ID` - Your AWS access key
- `AWS_SECRET_ACCESS_KEY` - Your AWS secret key

### 2. Pulumi Access Token
- `PULUMI_ACCESS_TOKEN` - Token from Pulumi Cloud

---

## How to Add Secrets to GitHub

1. Go to your repository: https://github.com/nwokehenry90/lab8
2. Click **Settings** (top menu)
3. In left sidebar, click **Secrets and variables** → **Actions**
4. Click **New repository secret**
5. Add each secret one by one:

### Adding AWS_ACCESS_KEY_ID:
- Name: `AWS_ACCESS_KEY_ID`
- Secret: `<your-aws-access-key>`
- Click **Add secret**

### Adding AWS_SECRET_ACCESS_KEY:
- Name: `AWS_SECRET_ACCESS_KEY`
- Secret: `<your-aws-secret-key>`
- Click **Add secret**

### Adding PULUMI_ACCESS_TOKEN:
- Name: `PULUMI_ACCESS_TOKEN`
- Secret: `<your-pulumi-token>`
- Click **Add secret**

---

## Getting Your Credentials

### AWS Credentials:
1. Log into AWS Console
2. Go to IAM → Users → Your User
3. **Security credentials** tab
4. Click **Create access key**
5. Choose **Command Line Interface (CLI)**
6. Copy both Access Key ID and Secret Access Key

### Pulumi Access Token:
1. Go to https://app.pulumi.com/
2. Click your profile → **Settings**
3. Click **Access Tokens** (left sidebar)
4. Click **Create Token**
5. Name it "GitHub Actions Lab8"
6. Copy the token (shown only once!)

---

## Verification

After adding all secrets, you should see 3 secrets listed:
- ✅ AWS_ACCESS_KEY_ID
- ✅ AWS_SECRET_ACCESS_KEY
- ✅ PULUMI_ACCESS_TOKEN

---

## Next Steps

Once secrets are configured:
1. Push your code to GitHub
2. The deploy workflow will run automatically on push to main
3. The destroy workflow can be manually triggered from Actions tab

---

## Important Notes

⚠️ **Security Best Practice**: For production, use OIDC authentication instead of static credentials (covered in part d of the lab).

⚠️ **Never commit secrets** to your repository - they must only be stored in GitHub Secrets.
