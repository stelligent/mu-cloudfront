# mu-cloudfront
Extension to create a CloudFront distribution in front of the ALB for a mu environment.  Additionally, this will create an S3 bucket for static resources.

Sample usage:

```
## Specify the id of an ACM cert for CloudFront to use (must be in us-east-1)
parameters:
  mu-loadbalancer-acceptance:
    CloudFrontCert: "0000000-0000-0000-0000-000000000"

extensions:
- url: https://github.com/stelligent/mu-cloudfront/archive/v0.7.zip
```
## Why is us-east-1 required?

[AWS Cloudfront documentation](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/cnames-and-https-requirements.html#https-requirements-aws-region) states that:
```
If you want to require HTTPS between viewers and CloudFront, you must change the AWS region to US East (N. Virginia) in the AWS Certificate Manager console before you request or import a certificate.
```
Cloudfront is a global service, and AWS Certificate Manager is regional. Therefore, one region had to be choisen to provide the certificates. They chose N. Virginia (us-east-1).