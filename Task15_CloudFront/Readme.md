Objective:
Deliver content globally using CloudFront CDN.

Description:
A CloudFront distribution was created with an S3 origin to improve performance and availability of content.


CloudFront Name: task15-cloudfront

Objective:
To use CloudFront CDN with S3 static website so that website loads faster from nearest AWS edge location.

What I did step by step:

1. First, I already had a static website hosted in S3 bucket.
2. Then I went to AWS Console → CloudFront → Create distribution.
3. In Origin domain, I selected my S3 bucket (static website bucket).
4. I kept origin settings default and allowed CloudFront to access the S3 bucket.
5. I enabled Origin Access Control (OAC) and allowed CloudFront to update bucket policy.
6. In Settings, I added Default root object as:
   index.html
7. I enabled HTTP/2 and IPv6 for better performance.
8. I created the CloudFront distribution with name:
   task15-cloudfront
9. I waited until the distribution status became "Deployed".
10. After deployment, I opened the CloudFront distribution domain URL in browser.
11. My S3 static website opened successfully using CloudFront CDN.

Outcome:
CloudFront successfully delivered the S3 static website using CDN. Website is now accessible globally with better performance.

Services Used:
- Amazon S3
- Amazon CloudFront

Proof:
- Screenshot of CloudFront distribution (Deployed status)
- Screenshot of website opened using CloudFront URL
Result:
Content delivered using CDN.
