---
subcategory: "Lambda"
layout: "aws"
page_title: "AWS: aws_lambda_provisioned_concurrency_config"
description: |-
  Manages a Lambda Provisioned Concurrency Configuration
---


<!-- Please do not edit this file, it is generated. -->
# Resource: aws_lambda_provisioned_concurrency_config

Manages a Lambda Provisioned Concurrency Configuration.

~> **NOTE:** Setting `skipDestroy` to `true` means that the AWS Provider will _not_ destroy a provisioned concurrency configuration, even when running `terraform destroy`. The configuration is thus an intentional dangling resource that is _not_ managed by Terraform and may incur extra expense in your AWS account.

## Example Usage

### Alias Name

```typescript
// Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { Token, TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { LambdaProvisionedConcurrencyConfig } from "./.gen/providers/aws/lambda-provisioned-concurrency-config";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    new LambdaProvisionedConcurrencyConfig(this, "example", {
      functionName: Token.asString(awsLambdaAliasExample.functionName),
      provisionedConcurrentExecutions: 1,
      qualifier: Token.asString(awsLambdaAliasExample.name),
    });
  }
}

```

### Function Version

```typescript
// Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { Token, TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { LambdaProvisionedConcurrencyConfig } from "./.gen/providers/aws/lambda-provisioned-concurrency-config";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    new LambdaProvisionedConcurrencyConfig(this, "example", {
      functionName: Token.asString(awsLambdaFunctionExample.functionName),
      provisionedConcurrentExecutions: 1,
      qualifier: Token.asString(awsLambdaFunctionExample.version),
    });
  }
}

```

## Argument Reference

The following arguments are required:

* `functionName` - (Required) Name or Amazon Resource Name (ARN) of the Lambda Function.
* `provisionedConcurrentExecutions` - (Required) Amount of capacity to allocate. Must be greater than or equal to `1`.
* `qualifier` - (Required) Lambda Function version or Lambda Alias name.

The following arguments are optional:

* `skipDestroy` - (Optional) Whether to retain the provisoned concurrency configuration upon destruction. Defaults to `false`. If set to `true`, the resource in simply removed from state instead.

## Attributes Reference

In addition to all arguments above, the following attributes are exported:

* `id` - Lambda Function name and qualifier separated by a comma (`,`).

## Timeouts

[Configuration options](https://developer.hashicorp.com/terraform/language/resources/syntax#operation-timeouts):

* `create` - (Default `15M`)
* `update` - (Default `15M`)

## Import

A Lambda Provisioned Concurrency Configuration can be imported using the `functionName` and `qualifier` separated by a comma (`,`), e.g.,

```
$ terraform import aws_lambda_provisioned_concurrency_config.example my_function,production
```

<!-- cache-key: cdktf-0.17.1 input-2faef0ec36909d612dbc8a4a3b8d1b6d3e1f99105ec8b1690a6882051a890680 -->