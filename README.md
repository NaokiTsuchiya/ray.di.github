# Ray.Di templates

## Usage


### coding-standards.yml

指定するPHPのバージョンを`php_version`で指定します。（他の設定ファイルでも同様）
Specifies the PHP version to run.　(The same is applied to other configuration files.)

```yaml
name: Coding Standards

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  cs:
    uses: ray-di/.github/.github/workflows/coding-standards.yml@v1
    with:
      php_version: 8.1
```

### continuous-integration.yml

２つのバージョンがあります。通常の`v1`と時期バージョンのPHPをテストする`next_stable`です。

There are two versions available. The regular `v1` version and the `next_stable` version, which tests the current version of PHP.

#### v1

```yaml
name: Continuous Integration

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  ci:
    uses: ray-di/.github/.github/workflows/continuous-integration.yml@v1
    with:
      old_stable: '["7.4", "8.0"]'
      current_stable: 8.1
```

#### next_stable

```yaml
name: Continuous Integration

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  ci:
    uses: ray-di/.github/.github/workflows/continuous-integration.yml@next_stable
    with:
      old_stable: '["7.4", "8.0"]'
      current_stable: 8.1
      next_stable: 8.2
```

### static-analysis.yml

[ComposerRequireChecker](https://github.com/maglnet/ComposerRequireChecker) のconfigファイル`composer-require-checker.json`があるときは`has_crc_config`をtrueにします。ない時はfalseにするか`has_crc_config`の指定そのものを取り除きます。

If the config file `composer-require-checker.json` for [ComposerRequireChecker](https://github.com/maglnet/ComposerRequireChecker) is present, set `has_ crc_config` to true. If not, set it to false or remove the `has_crcrc_config` specification itself.

```yaml
name: Static Analysis

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  sa:
    uses: ray-di/.github/.github/workflows/static-analysis.yml@v1
    with:
      php_version: 8.1
      has_crc_config: true
```

## GH actions workflow templates

* [Github docs about sharing workflows](https://docs.github.com/en/actions/learn-github-actions/sharing-workflows-with-your-organization#using-a-workflow-template)
* [Setup PHP in GitHub Actions](https://bestofphp.com/repo/shivammathur-setup-php-php-miscellaneous).

