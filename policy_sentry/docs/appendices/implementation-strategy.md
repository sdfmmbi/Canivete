Implementation Strategy
=======================

In the context of your overall organization strategy for AWS IAM, we
recommend using a few measures for locking down your AWS environments
with IAM:

1.  Use [Policy Sentry](https://github.com/salesforce/policy_sentry/) to
    create [Identity-based
    policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_identity-vs-resource.html)
2.  Use Service Control Policies (SCPs) to lock down available API calls
    per account.
    -   A great collection of SCPs can be found [on
        asecure.cloud](https://asecure.cloud/l/scp/).
    -   Control Tower has some excellent guidance on strategy for SCPs
        in their documentation. Note that they call it "Guardrails"
        but they are mostly SCPs. See the docs
        [here](https://docs.aws.amazon.com/controltower/latest/userguide/guardrails-reference.html)
3.  Use
    [Repokid](https://medium.com/netflix-techblog/introducing-aardvark-and-repokid-53b081bf3a7e)
    to revoke out of date policies as your application/roles mature.
4.  Use [Resource-based
    policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_identity-vs-resource.html)
    for all services that support them.
    -   A list of which services support resource-based policies can be
        found [in the AWS documentation
        here](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html).
5.  Never provision infrastructure manually; use Infrastructure as Code
    -   I highly suggest Terraform for IAC over other alternatives such
        as CloudFormation, Chef, or Puppet. Yevgeniy Brikman explains
        the reasons very well in [this Gruntwork.io blog
        post](https://blog.gruntwork.io/why-we-use-terraform-and-not-chef-puppet-ansible-saltstack-or-cloudformation-7989dad2865c).
    -   I also suggest reading HashiCorp's [Unlocking the Cloud
        Operating Model
        Whitepaper](https://www.hashicorp.com/cloud-operating-model).
