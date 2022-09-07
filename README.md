# CloudFormation example template for AWS WAF
This template will deploy a WebACL that includes the baseline rule group of AWS managed rules and a rate-based rule. Also, create CloudWatch logs group for AWS WAF as the destination of AWS WAF logs.

WebACL includes the following rules set as COUNT mode:
* [Core rule set (CRS) managed rule group](https://docs.aws.amazon.com/waf/latest/developerguide/aws-managed-rule-groups-baseline.html#aws-managed-rule-groups-baseline-crs)
* [Known bad inputs managed rule group](https://docs.aws.amazon.com/waf/latest/developerguide/aws-managed-rule-groups-baseline.html#aws-managed-rule-groups-baseline-known-bad-inputs)
* [Rate-based rule for All requests](https://docs.aws.amazon.com/waf/latest/developerguide/waf-rule-statement-type-rate-based.html)

## Installation:
To do the installation, click the Launch Stack button below and fill in the required parameters, Scope (CLOUDFRONT or REGIONAL) and WebACL name. Then click Next, and click Create stack on the last screen.

![Create Stack Image](/images/create-stack.png)



[![launch-stack](https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png)][1]
[Sample template](/aws-waf-template.yaml)

[1]: https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=cfn-example-waf&templateURL=https://s3.amazonaws.com/ytkoka-resources/cfn-example-aws-waf/aws-waf-template.yaml

[![launch-stack](https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png)][2]
[Sample template with the log filter as COUNT, BLOCK and EXCLUDED_AS_COUNT](/aws-waf-template-loggingfilter.yaml)

[2]: https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=cfn-example-waf&templateURL=https://s3.amazonaws.com/ytkoka-resources/cfn-example-aws-waf/aws-waf-template-loggingfilter.yaml

This template does not include the AWS resource to associate with WebACL. Please associate your AWS resource (CloudFront, ALB, API gateway )to the WebACL created by this template. [see here for instructions](https://docs.aws.amazon.com/waf/latest/developerguide/web-acl-associating-aws-resource.html)
