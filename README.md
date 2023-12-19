# Ray.Di templates

Perform unit tests on the PHP versions supported by [Supported Versions](https://www.php.net/supported-versions.php) and perform static analysis and coding standard inspections on the latest versions.

If you want to change the PHP version, use the [v1](https://github.com/ray-di/.github/tree/v1) or [next_stable](https://github.com/ray-di/.github/tree/next_stable) branch.

## Usage

### coding-standards.yml

```yaml
name: Coding Standards

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  cs:
    uses: ray-di/.github/.github/workflows/coding-standards.yml@v2
```

### continuous-integration.yml

```yaml
name: Continuous Integration

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  ci:
    uses: ray-di/.github/.github/workflows/continuous-integration.yml@v2
    with:
      script: demo/run.php
```

If you have a script you want to run, such as demo, specify it with `script`.


### static-analysis.yml

```yaml
name: Static Analysis

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  sa:
    uses: ray-di/.github/.github/workflows/static-analysis.yml@v2
```

If the config file `composer-require-checker.json` for [ComposerRequireChecker](https://github.com/maglnet/ComposerRequireChecker) is present, set `has_ crc_config` to true. If not, set it to false or remove the `has_crcrc_config` specification itself.

## GH actions workflow templates

* [Github docs about sharing workflows](https://docs.github.com/en/actions/learn-github-actions/sharing-workflows-with-your-organization#using-a-workflow-template)
* [Setup PHP in GitHub Actions](https://bestofphp.com/repo/shivammathur-setup-php-php-miscellaneous).

