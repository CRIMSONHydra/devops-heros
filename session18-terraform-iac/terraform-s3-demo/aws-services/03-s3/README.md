# S3 - Simple Storage Service (Storage)

## What is S3?
S3 is AWS storage for files of any type. You can store a very large amount of data, and it is very durable (99.999999999%). You access it over the internet using a web console, CLI, or API.

## Buckets
A bucket is a container that holds your files in S3. A bucket name must be unique in the whole world. Each bucket lives in one AWS region.

## Objects
An object is a file stored in a bucket. It has the data, a name called a key (like `images/cat.png`), and some metadata. One object can be up to 5 TB.

## Storage classes
Storage classes let you pick a price based on how often you use the data. `Standard` is for frequent access, `Standard-IA` is for rare access, and `Glacier` is for cheap long-term archives. `Intelligent-Tiering` moves data for you automatically.

## Versioning
Versioning keeps every version of an object when you change or delete it. This helps you get back an old file if you overwrite or delete it by mistake. Once on, it can be suspended but not fully turned off.

## Lifecycle policies
A lifecycle policy automatically moves or deletes objects after some time. For example, move files to Glacier after 90 days and delete them after 365 days. This saves money.

## Encryption
S3 can encrypt your data so others cannot read it. At rest, you can use SSE-S3 (AWS keys), SSE-KMS (your KMS keys), or client-side encryption. All new objects are encrypted by default, and data in transit is protected with HTTPS.

## Bucket policies
A bucket policy is a JSON rule attached to a bucket that says who can access it. For example, allow one IAM role to read, or deny any request that does not use HTTPS. Keep "Block Public Access" on unless you really need public files.

## Common use cases
- Store images, videos, and user uploads.
- Backups and disaster recovery.
- Host static websites.
- Data lakes and log storage.
- Store Terraform state files.
