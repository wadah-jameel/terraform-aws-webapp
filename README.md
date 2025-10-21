# AWS Static Website with Terraform

A beginner-friendly Terraform project that deploys a static website using AWS S3. This project demonstrates Infrastructure as Code (IaC) principles and is perfect for learning Terraform basics.

## 🌟 Features

- Static website hosting on AWS S3
- Automated infrastructure deployment
- Public access configuration
- Custom error page handling
- Easy teardown and cleanup

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- [Terraform](https://www.terraform.io/downloads) (v1.0 or higher)
- [AWS CLI](https://aws.amazon.com/cli/)
- An AWS account with appropriate permissions

## 🔧 AWS Configuration

1. Install and configure AWS CLI:
```bash
aws configure
```

2. Enter your AWS credentials when prompted:
   - AWS Access Key ID
   - AWS Secret Access Key
   - Default region (e.g., `us-east-1`)
   - Default output format (e.g., `json`)

## 📁 Project Structure

```
terraform-website/
├── main.tf              # Terraform configuration
└── website/
    ├── index.html       # Homepage
    └── error.html       # 404 error page
```

## 🚀 Getting Started

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/terraform-aws-website.git
cd terraform-aws-website
```

### Step 2: Initialize Terraform

```bash
terraform init
```

This downloads the required AWS provider plugins.

### Step 3: Review the Plan

```bash
terraform plan
```

This shows what resources Terraform will create without actually creating them.

### Step 4: Deploy the Infrastructure

```bash
terraform apply
```

Type `yes` when prompted to confirm. Terraform will create:
- An S3 bucket with a unique name
- Website configuration
- Public access settings
- Bucket policy for public read access
- Upload your HTML files

### Step 5: Access Your Website

After deployment completes, Terraform will output your website URL:

```
website_url = "my-terraform-website-abc123.s3-website-us-east-1.amazonaws.com"
```

Open this URL in your browser to see your website!

## 🎨 Customizing Your Website

Edit the HTML files in the `website/` directory:

- `website/index.html` - Your main homepage
- `website/error.html` - Custom 404 error page

After making changes, redeploy:

```bash
terraform apply
```

## 🧹 Cleanup

To avoid AWS charges, destroy all resources when done:

```bash
terraform destroy
```

Type `yes` to confirm. This removes all created resources.

## 📚 What You'll Learn

- Creating and configuring S3 buckets
- Managing public access policies
- Uploading files to S3 with Terraform
- Using Terraform outputs
- Infrastructure as Code best practices

## 💰 Cost Considerations

This project uses AWS S3 static website hosting, which is:
- Included in AWS Free Tier (12 months)
- Very low cost after free tier (~$0.023/GB for storage)
- No charges for inbound data transfer

Remember to run `terraform destroy` when you're done to avoid any charges.

## 🔒 Security Note

This configuration makes your S3 bucket publicly accessible for website hosting. Do not store sensitive information in this bucket.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the MIT License.

## 📞 Support

If you encounter any issues or have questions:
- Open an issue in this repository
- Check [Terraform AWS Provider Documentation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
- Review [AWS S3 Documentation](https://docs.aws.amazon.com/s3/)

## 🎯 Next Steps

Ready to expand your skills? Try these enhancements:
- Add CloudFront CDN for faster global delivery
- Configure a custom domain name
- Add CSS and JavaScript files
- Implement HTTPS with SSL certificates
- Set up multiple environments (dev/staging/prod)
