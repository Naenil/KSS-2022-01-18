# KSS - Fast and cost-effective website deployment using AWS CloudFront - Demo

## Static website generation using next.js

### From scratch

* Create a next.js project with npx `create-next-app`
* In the scripts section of package.json, add `"build": "next build && next export",`
* In `next.config.js`,  add the following content:

```js
module.exports = {
  reactStrictMode: true,
  images: {
    loader: 'akamai',
    path: '',
  },
}
```

* You can now produce a static website using `yarn build`

### Using this repository

* Install dependencies with `yarn install`
* You can now produce a static website using `yarn build`

## Bucket creation

### Create the bucket in Amazon S3

* Public access needs to be granted

### Upload the files there

* Using the AWS CLI, you want to run
* `aws s3 sync kss/out s3://YOUR_BUCKET/`

## CDN creation

* [Using this method](https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serve-static-website/)
* For Origin domain, select the bucket that you created.
* For S3 bucket access, select Yes use OAI (bucket can restrict access to only CloudFront).
* For Origin access identity, select Create new OAI. Then, enter the OAI name and choose Create.
* For Bucket policy, select Yes, update the bucket policy.
* Edge locations: select only north America and Europe
* Have index.html as default root object
* You then have a cloudfront url

## Optional - DNS setup

* Make ALIAS on Route53, or CNAME records anywhere else to point towards [distributioj].cloudfront.net