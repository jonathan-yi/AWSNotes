### What is IAM?
  - Allows you to manage users and level of access to the AWS Console

### What Does IAM give you?
  - Centralized control of AWS account
  - Shared access to AWS account
  - Granular Permissions
  - Identity Federation
  - Multifactor Authentication
  - Provide temp access for users/devices and services where necessary
  - Allows you to set up own password rotation policy
  - Intergrates with many different AWS services
  - Support PCI DSS Compliance

### Critical Terms:
- Users - End Users (people)
- Groups - collection of users under one sef of permissions
- Roles - you create roles and can assign them to AWS resources
- Policies - document that defines one (or more permissions) that you attach to users or to groups (Made of JSON)

- Users, Groups, Roles will all be globally available and are not tied to a specific region.
- AWS recommends to create users then group into groups and assign permissions for groups

- Programmatic access allows your application to access AWS or SDK/CLI on desktop
- When you create a user you can use the Access Key ID and Secret Access Key to use CLI/API/SDK to interact with AWS. But when using AWS console you use the password to login.

- Root account is account created when first setup AWS account has complete Admin access.
- New Users have NO permissions when first created, but are assigned Access Key ID and Secret Access Keys when first created.
- Always setup MFA on root account
- IAM you can create and customize your own password rotation policies

- Power User Access allows access to all AWS services except for management of groups and users within IAM
