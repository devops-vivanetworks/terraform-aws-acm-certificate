# terraform-aws-acm-certificate

[![Terraform Version](https://img.shields.io/badge/Terraform%20Version->=0.13.0,<=0.13.7-blue.svg)](https://releases.hashicorp.com/terraform/)
[![Release](https://img.shields.io/github/release/traveloka/terraform-aws-acm-certificate.svg)](https://github.com/traveloka/terraform-aws-acm-certificate/releases)
[![Last Commit](https://img.shields.io/github/last-commit/traveloka/terraform-aws-acm-certificate.svg)](https://github.com/traveloka/terraform-aws-acm-certificate/commits/master)
[![Issues](https://img.shields.io/github/issues/traveloka/terraform-aws-acm-certificate.svg)](https://github.com/traveloka/terraform-aws-acm-certificate/issues)
[![Pull Requests](https://img.shields.io/github/issues-pr/traveloka/terraform-aws-acm-certificate.svg)](https://github.com/traveloka/terraform-aws-acm-certificate/pulls)
[![License](https://img.shields.io/github/license/traveloka/terraform-aws-acm-certificate.svg)](https://github.com/traveloka/terraform-aws-acm-certificate/blob/master/LICENSE)
![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)

## Description

Terraform module to create TLS/SSL certificate in Amazon Certificate Manager (ACM) using DNS validation by creating required Route53 validation record in the given Route53 hosted zone.

## Table of Content

* [terraform-aws-acm-certificate](#terraform-aws-acm-certificate)
   * [Description](#description)
   * [Table of Content](#table-of-content)
   * [Prerequisites](#prerequisites)
   * [Dependencies](#dependencies)
   * [Terraform Version](#terraform-version)
   * [Requirements](#requirements)
   * [Providers](#providers)
   * [Modules](#modules)
   * [Resources](#resources)
   * [Inputs](#inputs)
   * [Outputs](#outputs)
   * [Contributing](#contributing)
   * [License](#license)

## Prerequisites

In order to provision this module, it is require some information from an existing resources as input parameter, those resources are:

- Route53 Zone, input variable that require the information from this resource are, `hosted_zone_name`

## Dependencies

Doesn't have any dependencies to any other Terraform module

## Terraform Versions

Created and tested using Terraform version `0.11.14`
The latest stable version of Terraform which this module tested working is Terraform `0.13.7` on 2021/09/29


<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.13 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_acm_certificate.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/acm_certificate) | resource |
| [aws_acm_certificate_validation.dns_validation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/acm_certificate_validation) | resource |
| [aws_route53_record.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/route53_record) | resource |
| [aws_route53_zone.zone](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/route53_zone) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_certificate_name"></a> [certificate\_name](#input\_certificate\_name) | Name of the ACM certificate. | `string` | n/a | yes |
| <a name="input_description"></a> [description](#input\_description) | Free form description of this ACM certificate. | `string` | n/a | yes |
| <a name="input_domain_name"></a> [domain\_name](#input\_domain\_name) | Domain name the certificate is issued for. | `string` | n/a | yes |
| <a name="input_environment"></a> [environment](#input\_environment) | Environment this ACM certificate belongs to. | `string` | n/a | yes |
| <a name="input_hosted_zone_name"></a> [hosted\_zone\_name](#input\_hosted\_zone\_name) | Need for DNS validation, hosted zone name where record validation will be stored. | `string` | n/a | yes |
| <a name="input_product_domain"></a> [product\_domain](#input\_product\_domain) | Abbreviation of the product domain this ACM certificate belongs to. | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_acm_certificate_arn"></a> [acm\_certificate\_arn](#output\_acm\_certificate\_arn) | arn of acm certificate |
| <a name="output_acm_certificate_dns_validation_record"></a> [acm\_certificate\_dns\_validation\_record](#output\_acm\_certificate\_dns\_validation\_record) | record which is used to validate acm certificate |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Contributing

This module accepting or open for any contributions from anyone, please see the [CONTRIBUTING.md](https://github.com/traveloka/terraform-aws-elasticache-memcached/blob/master/CONTRIBUTING.md) for more detail about how to contribute to this module.

## License

This module is under Apache License 2.0 - see the [LICENSE](https://github.com/traveloka/terraform-aws-elasticache-memcached/blob/master/LICENSE) file for details.