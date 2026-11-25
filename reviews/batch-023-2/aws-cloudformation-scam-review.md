# AWS CloudFormation review: features, pricing and buyer considerations

**Last editorial review:** 2026-11-17  
**Category:** Infrastructure as Code Service  
**Method:** Source-led desk review; no hands-on testing is claimed.

AWS CloudFormation provisions and updates AWS resources from templates and stack operations. The service is generally not separately charged for native resource providers, but the resources created during successful or failed stack attempts can incur normal AWS charges.

## Editorial verdict

CloudFormation can make infrastructure changes reviewable and repeatable when templates, change sets and stack ownership are managed carefully. Its most important cost caveat is that a failed deployment does not erase charges for resources that were already created; inspect rollback results and clean up orphaned infrastructure.

## AWS CloudFormation review: infrastructure defined as templates

CloudFormation lets teams describe AWS resources in templates and manage them through stacks. This can make infrastructure changes reviewable in version control and repeatable across environments. A template does not make a change harmless by itself: an update can replace a database or expose a resource if the declared properties and lifecycle policy are wrong. The main benefit is that the intended configuration can be inspected and rehearsed before it is applied.

Use change sets for non-trivial updates and require an owner to review resources that may be replaced, deleted or made public. Store templates with version history, validate them and test in a separate account or environment. Document retained resources and import behavior. Treat infrastructure code like application code: changes need review, a deployment plan and a rollback strategy that has been exercised.


## CloudFormation pricing and the cost of resources in a stack

AWS says CloudFormation itself has no additional charge for AWS, Alexa and Custom resource providers. Customers still pay for the underlying resources, such as compute, storage and load balancers, at the normal service rates. Third-party resource provider operations outside the listed namespaces may incur handler-operation charges. The service’s apparent free status should therefore never be used as a cost estimate for the architecture described by a template.

Build the estimate from every resource in the template, including resources that are created only temporarily during an update. Include region, size, storage, network and data transfer. For nested stacks or modules, expand the full resource tree so that a small top-level template does not conceal a large deployment. Use cost tags or stack metadata to connect generated resources to their owning team.


## Failed CloudFormation stacks, rollback and orphaned resources

CloudFormation’s FAQ states that charges for AWS resources created during stack instantiation apply even if the stack as a whole fails. A rollback can therefore be financially relevant, especially if a partially created resource runs for hours or days before someone notices it. Some resources may be retained by policy, and a failed custom resource can leave an external resource whose lifecycle needs separate attention.

After a failed deployment, inspect the stack events and actual account inventory. Confirm which resources were deleted, retained or left in a failed state. Use a safe retry plan rather than repeatedly submitting the same template. Test cleanup behavior in a development account and keep a checklist for databases, snapshots, IP addresses and third-party resources. A stack marked failed is not proof that nothing was provisioned.


## Change sets, drift and operational governance

Change sets help show how an update would affect the stack before execution. Drift detection can identify some differences between declared and deployed configuration, although not every property or external side effect is necessarily covered. Manual console edits can make the template an inaccurate description of reality, while a future deployment may reset or replace those changes.

Establish a policy for how urgent manual fixes are reconciled back into source control. Track stack ownership, required approvals, deployment roles and the accounts where a template can run. Review failure notifications and retention of stack events. For high-impact data resources, add explicit deletion safeguards and test restore procedures. Keep template parameters and secret references separate from public source code.


## CloudFormation alternatives and the SCAM Review question

Compare CloudFormation with Terraform, Pulumi and other infrastructure-as-code tools using the same AWS resources and team workflow. Include state management, provider coverage, review steps, drift handling, resource imports and the risk of failed changes. A first-party AWS tool may fit teams that want native stack operations; a multi-cloud team may value a broader provider ecosystem. The most important criterion is whether the team can understand, review and recover from the generated plan.

AWS’s official pricing and FAQ pages describe CloudFormation and explicitly distinguish the orchestration layer from billable resources; they do not establish that CloudFormation is a scam. This review did not apply a template to an AWS account. Before deployment, inspect the change set, estimate resource charges, verify rollback and deletion behavior, review third-party providers and monitor resources left after a failed stack.


## Features and decision criteria

- Infrastructure templates and stack deployments
- Change sets for reviewing intended modifications
- Stack rollback and resource lifecycle management
- Drift detection and reusable modules

## Pricing considerations

A free CloudFormation control plane does not make a stack’s resources free. Estimate all created resources, account for region and duration, inspect rollback state and verify deletion of any retained resources.

## Sources and further reading

- [AWS CloudFormation pricing](https://aws.amazon.com/cloudformation/pricing/)
- [AWS CloudFormation FAQ and failed-stack billing](https://aws.amazon.com/cloudformation/faqs/)
- [CloudFormation user guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)
- [CloudFormation change sets documentation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-changesets.html)
- [AWS CloudFormation on Wikipedia](https://en.wikipedia.org/wiki/AWS_CloudFormation)
- [AWS CloudFormation website](https://aws.amazon.com/cloudformation/)
- [saashub listing](https://www.saashub.com/aws-cloudformation)

For the complete Roseram buyer guide, see [AWS CloudFormation review](https://roseram.com/reviews/scams/aws-cloudformation-scam-review).

Roseram publishes this review and operates a commercial AI workspace. Check current vendor terms, pricing and availability with the original sources before purchasing.
