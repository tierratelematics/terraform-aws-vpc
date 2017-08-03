# terraform-aws-vpc

This repository is a set of Terraform modules for building infrastructure with AWS VPC.

## Quickstart

The easiest way to get the modules and running is by creating a Terraform definition for it, copy this snippet in a file
named `main.tf`:

```hcl

module "vpc" {
  source = "git::https://github.com/tierratelematics/terraform-aws-vpc.git//modules/vpc?ref=0.1.0"

  project            = "${var.project}"
  environment        = "${var.environment}"

  cidr               = "${var.cidr}"
  external_subnets   = "${var.external_subnets}"
  internal_subnets   = "${var.internal_subnets}"
  availability_zones = "${var.availability_zones}"
}
```

The ecample values for the variable are:

```hcl
project = "sample"

environment = "dev"

aws_region = "eu-west-1"

internal_subnets = ["10.30.0.0/19", "10.30.64.0/19", "10.30.128.0/19"]

external_subnets = ["10.30.32.0/20", "10.30.96.0/20", "10.30.160.0/20"]

availability_zones = ["us-west-2a", "us-west-2b", "us-west-2c"]
```

## Reference

* [Pratical VPC Design](https://medium.com/aws-activate-startup-blog/practical-vpc-design-8412e1a18dcc) a  useful article on how to design a VPC in AWS.
* [What is the recommended CIDR when creating VPC on AWS?](https://serverfault.com/questions/630022/what-is-the-recommended-cidr-when-creating-vpc-on-aws)
* [Subnet Mask Cheat Sheet](https://www.aelius.com/njh/subnet_sheet.html)

## Credits

Many many ideas and code for this project originated from the awesome work from the great folks at https://github.com/segmentio/stack. Check out their work on Terraform and AWS.

## License

Copyright 2017 Tierra SpA

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
