# TFLint Ruleset NewRelic
[![Build Status](https://github.com/Tensho/tflint-ruleset-newrelic/workflows/build/badge.svg?branch=main)](https://github.com/terraform-linters/tflint-ruleset-template/actions)

Custom [NewRelic](https://newrelic.com) plugin.
See also [Writing Plugins](https://github.com/terraform-linters/tflint/blob/master/docs/developer-guide/plugins.md).

## Requirements

- TFLint v0.42+
- Go v1.22

## Installation

You can install the plugin with `tflint --init`. Declare a config in `.tflint.hcl` as follows:

```hcl
plugin "newrelic" {
  enabled = true

  version = "0.1.0"
  source  = "github.com/Tensho/tflint-ruleset-newrelic"
}
```

## Rules

|Name|Description|Severity|Enabled|Link|
| --- | --- | --- | --- | --- |
|aws_instance_example_type|Example rule for accessing and evaluating top-level attributes|ERROR|✔||
|aws_s3_bucket_example_lifecycle_rule|Example rule for accessing top-level/nested blocks and attributes under the blocks|ERROR|✔||
|google_compute_ssl_policy|Example rule with a custom rule config|WARNING|✔||
|terraform_backend_type|Example rule for accessing other than resources|ERROR|✔||

## Building the plugin

Clone the repository locally and run the following command:

```
$ make
```

You can easily install the built plugin with the following:

```
$ make install
```

You can run the built plugin like the following:

```
$ cat << EOS > .tflint.hcl
plugin "newrelic" {
  enabled = true
}
EOS
$ tflint
```
