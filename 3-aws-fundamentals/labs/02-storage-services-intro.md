# 2. Storage Services Intro
S3 -> Create bucket -> Bucket name (must be unique across the AWS), AWS Region: N Virginia, check "Block all public access". Bucket Versioning: if this is enabled, you can always revert to a older version of you documents, such as an older version of a website. Tags: if a tag is added, you can view costs by that tag, in the billing console. You can choose to enable/disable server-side encryption -> Create bucket. 

Upload -> Drag and drop files to the browser window -> Upload 

Then you can download the files. 

Each object has an Object URL, which can be opened directly, if the bucket is public. Otherwise, the access to the url will be denied. 

To delete the bucket: 
1. select this bucket in the buckets list -> Empty (you cannot delete a bucket that has objects in it)
2. select this bucket in the buckets list -> Delete
