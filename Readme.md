# S3 policy.

  [S3 policy][https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html] generation for client-side uploads. By default, `Content-Type` and
  `Content-Length` form fields are __required__, but can contain any value.

## Options

Create an s3 policy and signature via `opts`:

 - `acl` acl such as "public-read"
 - `expires` expiration date
 - `secret` s3 secret
 - `bucket` bucket name
 - `key` access key
 - `name` restrict key to prefix [""]
 - `type` restrict content-type prefix [""]
 - `length` max size restriction
 - `conditions` an optional Array of custom "conditions" to include in the policy

An object with `.signature` and `.policy` is returned.

## Example

```js
var policy = require('s3-policy');

var p = policy({
  secret: 'something',
  length: 5000000,
  bucket: 'i.cloudup.com',
  key: 'asdfasdfaewrw',
  expires: new Date(Date.now() + 60000),
  acl: 'public-read'
});

console.log(p.policy);
console.log(p.signature);
```













































































