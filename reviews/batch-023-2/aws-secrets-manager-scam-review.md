# AWS Secrets Manager review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Cloud Secrets Management Service  
**Method:** Source-led desk review; no hands-on testing is claimed.

AWS Secrets Manager stores and retrieves credentials and supports rotation workflows. Its pricing is based on stored secrets and API calls, with additional Lambda or KMS costs possible depending on rotation and encryption configuration.

## Editorial verdict

Secrets Manager can centralize application credentials and automate rotation, but cost and security depend on secret count, retrieval frequency, IAM scope and rotation design. Review the API call volume and permission graph as carefully as the price per secret.

## AWS Secrets Manager review: centralized credentials and rotation

AWS Secrets Manager stores secrets such as database credentials, API keys and other sensitive values, then provides applications with an authenticated retrieval path. It supports lifecycle and rotation workflows, including AWS Lambda functions for custom rotations. For a team with credentials spread through environment files and deployment scripts, a central service can improve change control and reduce accidental exposure if application roles are properly scoped.

The service does not repair an overbroad permission model. A workload role should retrieve only the secret it needs, and a user should not be able to read every credential because they can deploy one application. Trace which identity retrieves each secret and which environments can access it. Keep secret values out of logs and CI output, use separate values per environment and rotate credentials if they were committed to a repository.


## AWS Secrets Manager pricing: secret storage and API requests

AWS currently lists Secrets Manager at $0.40 per secret per month and $0.05 per 10,000 API calls. Its pricing examples show that both a growing number of credentials and frequent retrievals affect the monthly total. A short-lived secret may be billed for its storage duration, and AWS notes that rotation creates new versions without charging separately for each version. The exact amount depends on region and any eligible Free Tier credit available to the account.

Calculate secret count by application and environment, then estimate how often code retrieves each value. Fetching a password on every request may generate a different call pattern than caching it securely for a controlled period. Add rotation Lambda compute, customer-managed KMS keys and CloudTrail log storage where used. Tag secrets so finance can attribute cost, and set an owner and expiry date for temporary credentials that should not remain indefinitely.


## Secrets Manager rotation, availability and application behavior

Automatic rotation is only useful when the rotation workflow can change the credential at the source and the application can adopt the new value without interruption. AWS documentation describes custom rotation through Lambda, which carries its own service cost and operational failure modes. Rotation can also reveal hidden dependencies: an old connection pool, a second region or a third-party job may still rely on the previous password.

Test rotation on a non-production secret with a realistic client. Confirm that the database accepts the new credential, that active connections recover and that rollback behavior is understood. Avoid rotation schedules that create a deployment outage or leave a long-lived process with a stale secret. Monitor failures, alert an owner and provide a manual recovery path for a time-sensitive credential rotation.


## Secrets Manager IAM, encryption and audit checks

Secrets Manager integrates with IAM for authorization and AWS KMS for encryption. AWS says its managed key can be used without an additional KMS charge, while using customer-managed keys may incur the current KMS rate. CloudTrail can record management events, and associated storage or notification services may add cost. These controls support a governance process but do not guarantee that an organization’s setup meets a specific compliance obligation.

Review resource policies, identity policies and cross-account access for each secret. Use least privilege, rotate access keys and review audit records for unusual retrieval patterns. Confirm how break-glass access works and who can recover a deleted secret during its recovery window. Do not place the secret itself in tags or metadata. Test backups and recovery for critical credentials without exposing their values during the exercise.


## AWS Secrets Manager alternatives and the SCAM Review question

Compare Secrets Manager with AWS Systems Manager Parameter Store, a cloud-agnostic vault and a managed Kubernetes secrets workflow. Distinguish sensitive credentials that require rotation from ordinary configuration values that may not need the same features. Compare per-secret and API-call cost, integration effort, audit needs, cross-cloud reach, rotation support and recovery process. A lower storage fee is not a good trade if the alternative leaves secrets unrotated or broadly accessible.

AWS’s official product, pricing and user-guide pages describe a commercial secrets service with published usage meters; they do not establish that it is a scam. This review did not configure an AWS account or rotate live credentials. Before adoption, confirm regional pricing, API call volume, KMS and Lambda charges, IAM scope, secret lifecycle, CloudTrail retention and tested credential rotation.


## Features and decision criteria

- Encrypted storage and retrieval of application secrets
- Automatic rotation workflows for supported credentials
- IAM policies and audit logging through AWS services
- Integration paths for AWS services and applications

## Pricing considerations

Estimate total secret-hours and API calls. Rotation functions, custom KMS keys, CloudTrail, S3 log storage and notification services can add separate AWS charges.

## Sources and further reading

- [AWS Secrets Manager pricing](https://aws.amazon.com/secrets-manager/pricing/)
- [AWS Secrets Manager introduction and cost notes](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html)
- [Secrets Manager best practices](https://docs.aws.amazon.com/secretsmanager/latest/userguide/best-practices.html)
- [Secrets Manager monitoring and CloudTrail](https://docs.aws.amazon.com/secretsmanager/latest/userguide/monitoring.html)
- [AWS Secrets Manager on Wikipedia](https://en.wikipedia.org/wiki/AWS_Secrets_Manager)
- [AWS Secrets Manager website](https://aws.amazon.com/secrets-manager/)
- [saashub listing](https://www.saashub.com/aws-secrets-manager)

For the complete Roseram buyer guide, see [AWS Secrets Manager review](https://roseram.com/reviews/scams/aws-secrets-manager-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
