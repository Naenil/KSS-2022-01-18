# KSS - Fast and cost-effective website deployment using AWS CloudFront - Demo

## 1. Static website generation using next.js

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

## 2. Bucket creation

## 3. CDN creation

## 4. Optional - DNS setup