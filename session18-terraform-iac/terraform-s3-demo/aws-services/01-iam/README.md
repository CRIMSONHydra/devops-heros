# IAM - Identity and Access Management (Governance)

## What is IAM?
IAM is the AWS service that controls who can log in to AWS and what they can do. It is like a security guard that checks every request. IAM is free and works across your whole AWS account.

## Users
A user is one person or one app that needs access to AWS. Each user has their own name and credentials, like a password or access keys. Do not share one user between many people.

## Groups
A group is a collection of users. You attach permissions to the group, and every user in it gets them. For example, put all developers in a "Developers" group.

## Roles
A role is an identity with permissions that anyone (or any service) can temporarily "wear". It has no password or permanent keys. For example, an EC2 server can use a role to read from S3.

## Policies
A policy is a JSON document that lists what is allowed or denied. It says which actions (like `s3:GetObject`) can be done on which resources. You attach policies to users, groups, or roles.

```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": "s3:GetObject",
    "Resource": "arn:aws:s3:::my-bucket/*"
  }]
}
```

## Permissions
Permissions are the actual things an identity is allowed to do, like "read a file" or "start a server". They come from the policies attached to the identity. By default, everything is denied until you allow it.

## Least privilege
Least privilege means giving only the permissions that are really needed, and nothing more. If someone only needs to read one bucket, do not give them access to all of S3. This limits the damage if an account is hacked.

## IAM best practices
- Do not use the root account for daily work, and turn on MFA for it.
- Turn on MFA for all users.
- Use roles instead of long-term access keys.
- Give least privilege and review permissions often.
- Use groups to manage permissions instead of attaching to each user.

## Common use cases
- Give developers different access than admins.
- Let an EC2 or Lambda function call other AWS services safely.
- Let another AWS account access your resources using a role.
- Let CI/CD tools like GitHub Actions deploy to AWS without storing keys.
