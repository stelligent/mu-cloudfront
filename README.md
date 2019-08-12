# mu-cloudfront
Extension to create a CloudFront distribution in front of the ALB for a mu environment.  Additionally, this will create an S3 bucket for static resources.

Sample usage:

```
## Specify the id of an ACM cert for CloudFront to use
parameters:
  mu-loadbalancer-acceptance:
    CloudFrontCert: "0000000-0000-0000-0000-000000000"

extensions:
- url: https://github.com/stelligent/mu-cloudfront/archive/v0.71.zip
```



