# AWS Next.js with SST

A Next.js application deployed to AWS using SST (Serverless Stack) with TypeScript and Tailwind CSS.

## Quick Start

```bash
# Install dependencies
npm install

# Start local development
npm run dev

# Deploy to AWS
npm run deploy
```

## AWS Resources Created

When you deploy this Next.js application to AWS using SST, the following resources are automatically created:

### Core Infrastructure

- **S3 Buckets**

  - Static assets bucket for Next.js build files, images, CSS, and JavaScript
  - Server function deployment packages storage

- **CloudFront Distribution**

  - Global CDN for fast content delivery
  - Cache behaviors optimized for static vs dynamic content
  - Origin configurations pointing to S3 and Lambda functions

- **Lambda Functions**

  - Server-side rendering function for Next.js pages and API routes
  - Image optimization function (when using Next.js Image component)

- **IAM Roles & Policies**
  - Lambda execution roles with required permissions
  - CloudFront access policies for S3 bucket access

### Optional Resources

- **Route 53 Records** (if using custom domain)
- **ACM SSL Certificates** (if using HTTPS with custom domain)

### Resource Management

All resources are:

- Automatically provisioned and configured by SST
- Scoped to your personal stage name to avoid conflicts
- Managed through Infrastructure as Code (Pulumi)
- Easily torn down with `npx sst remove`

## Commands

```bash
npm run dev      # Start Next.js development server
npm run build    # Build Next.js application
npm run start    # Start production server locally
npm run deploy   # Deploy to AWS
npx sst remove   # Remove all AWS resources
npx sst list     # List deployed resources
```

## Tech Stack

- **Framework**: Next.js 16
- **Styling**: Tailwind CSS 4
- **Runtime**: React 19
- **Language**: TypeScript
- **Infrastructure**: SST 3 (Serverless Stack)
- **Cloud**: AWS

## Getting Started

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!
