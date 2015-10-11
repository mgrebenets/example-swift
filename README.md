Codecov Swift Example
=====================

[![Build Status](https://travis-ci.org/mgrebenets/example-swift.svg)](https://travis-ci.org/mgrebenets/example-swift) 
[![codecov.io](http://codecov.io/github/mgrebenets/example-swift/coverage.svg?branch=master)](http://codecov.io/github/mgrebenets/example-swift?branch=master)


This repository serves as an **example** on how to use [Codecov Global][4] for Swift.

## Usage
Enable "Gather coverage data" in your test scheme:

![gather coverage data](docs/gather_coverage_data.png)

# Travis CI

Add to your `.travis.yml` file.
```yml
language: swift # or objective-c
osx_image: xcode7
script: ./test.sh
after_success:
  - bash <(curl -s https://codecov.io/bash)
```

## Private Repos
> Set `CODECOV_TOKEN` in your environment variables.

Add to your `.travis.yml` file.
```yml
env:
  global:
    - CODECOV_TOKEN=:uuid-repo-token

after_success:
  - bash <(curl -s https://codecov.io/bash)
```

# Codecov
Make sure to specify **Ignore files** in the settings for your repo. You will find a textarea to add these settings in Codecov at `https://codecov.io/gh/OWNER/REPO/features/ignore`
```
Pods/.*
Applications/Xcode.app/.*
vendor/.*
Carthage/.*
build/.*
.*Tests.m
.*Tests.swift

# Add the folders containing your unit tests
# This ensures any test utility classes you create are also ignored
SwiftExampleTests/.*
SwiftExampleUITests/.*
```

View source and learn more about [Codecov Global Uploader][4]

[1]: https://codecov.io/
[2]: https://twitter.com/codecov
[3]: mailto:hello@codecov.io
[4]: https://github.com/codecov/codecov-python
