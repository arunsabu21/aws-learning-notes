# IAM (Identity and Access Management)

## What is IAM?

IAM (Identity and Access Management) is an AWS service used to securely manage access to AWS resources.

IAM helps control:

- Who can access AWS
- What resources they can access
- What actions they can perform

Using IAM, organizations can provide secure access to AWS services without sharing the Root User account.

---

## IAM Components

```text
IAM
├── Users
├── Groups
└── Policies
```

### Users

Represents an individual person or application that needs access to AWS.

Examples:

- Admin
- Developer
- Tester
- Application User

### Groups

A collection of IAM users.

Groups make permission management easier.

Example:

```text
Developers Group
├── dev1
├── dev2
└── dev3
```

Instead of assigning permissions to each user individually, permissions can be assigned to the group.

### Policies

Policies are JSON documents that define permissions.

They determine:

- Which AWS resources can be accessed
- Which actions can be performed
- Whether access is allowed or denied

Example:

```text
Allow:
- Read S3 Buckets

Deny:
- Delete S3 Buckets
```

---

# Root User

The Root User is the account owner created when an AWS account is first registered.

The Root User has unrestricted access to all AWS services and resources.

### Root User Permissions

- Full access to AWS services
- Access to billing and payment settings
- Create and manage IAM users
- Close the AWS account
- Modify account-level settings

### Best Practice

AWS recommends:

- Use the Root User only for account setup and critical tasks
- Enable Multi-Factor Authentication (MFA)
- Avoid daily usage of the Root User

```text
AWS Account
└── Root User
```

---

# IAM User

An IAM User is an identity created within an AWS account.

IAM Users are used by individuals who need access to AWS resources.

Each user can have different permissions based on their role.

### Purpose

Allows users to access AWS with specific permissions instead of using the Root User.

### Example

```text
AWS Account
├── Root User
├── Admin
├── Developer 1
├── Developer 2
└── Tester
```

### Benefits

- Improved Security
- Permission Control
- Activity Tracking
- Reduced Risk

---

## Real-World Example

A software company has:

```text
AWS Account
├── Root User
├── Admin
├── Backend Developer
├── Frontend Developer
└── Tester
```

Permissions:

| User | Permission |
|--------|--------|
| Admin | Full AWS Access |
| Backend Developer | EC2, RDS Access |
| Frontend Developer | S3 Access |
| Tester | Read-Only Access |

Each user receives only the permissions required for their job.

---

## Quick Summary

| Component | Purpose |
|------------|------------|
| Root User | Account Owner with Full Access |
| IAM User | Individual Identity |
| IAM Group | Collection of Users |
| IAM Policy | Defines Permissions |

### Memory Trick

```text
IAM
├── Users = Who?
├── Groups = Team?
└── Policies = What can they do?
```

IAM follows the principle of:

```text
Least Privilege Access
```

Give users only the permissions they need to perform their tasks.