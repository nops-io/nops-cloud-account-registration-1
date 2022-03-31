# Register Aws Account To NOPS Terraform Module

Terraform module to provision resources required to register an aws account to NOPS.

## Usage
```hcl
    module "register_aws_acc_to_nops" {
        source                  = NA
        version                 = NA

        ExternalId              = "12345"
        NopsApiKey              = "12345"
        AccNameToRegister       = "demo"
    }
```
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | < 4.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | < 4.0 |


## Resources

| Name | Type |
|------|------|
| [aws_cur_report_definition.cur_report_definition](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cur_report_definition) | resource |
| [aws_iam_role.nops_access_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_iam_role.nops_lambda_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_lambda_function.nops_register_aws_acc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lambda_function) | resource |
| [aws_s3_bucket.s3](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket) | resource |
| [aws_s3_bucket_policy.s3](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket_policy) | resource |
| [aws_caller_identity.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity) | data source |
| [aws_iam_policy_document.Policy_For_Bucket](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_iam_policy_document.Trusted_Policy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |
| [aws_lambda_invocation.nops_register_aws_acc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/lambda_invocation) | data source |
| [aws_region.current](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/region) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_AccNameToRegister"></a> [AccNameToRegister](#input\_AccNameToRegister) | Account name to register in nops. | `string` | n/a | yes |
| <a name="input_BucketName"></a> [BucketName](#input\_BucketName) | s3 bucket name for nops daily reports | `string` | `"nopsbucketforlogs"` | no |
| <a name="input_ExternalId"></a> [ExternalId](#input\_ExternalId) | External id required for cross account access role for nops | `string` | n/a | yes |
| <a name="input_NopsApiKey"></a> [NopsApiKey](#input\_NopsApiKey) | Nops api key to register aws accounts | `string` | n/a | yes |
| <a name="input_NopsPrivateKey"></a> [NopsPrivateKey](#input\_NopsPrivateKey) | Nops private key to generate signature for api request, it should be single line string (optional). | `string` | `""` | no |
| <a name="input_ReportName"></a> [ReportName](#input\_ReportName) | Nops daily generated report name | `string` | `"nopsbilling-daily-gzip"` | no |
| <a name="input_s3prefix"></a> [s3prefix](#input\_s3prefix) | Nops daily generated reports folder prefix | `string` | `"something"` | no |
| <a name="input_tags"></a> [tags](#input\_tags) | Tags to be applied to the resource | `map(any)` | `{}` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_output"></a> [output](#output\_output) | n/a |