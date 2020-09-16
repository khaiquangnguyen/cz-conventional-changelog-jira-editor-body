# cz-conventional-changelog-with-jiraid-detection

[![npm version](https://img.shields.io/npm/v/cz-conventional-changelog-with-jiraid-detection.svg?style=flat)](https://www.npmjs.org/package/cz-conventional-changelog-with-jiraid-detection)
[![npm downloads](https://img.shields.io/npm/dm/cz-conventional-changelog-with-jiraid-detection.svg?style=flat)](http://npm-stat.com/charts.html?package=cz-conventional-changelog-with-jiraid-detection&from=2020-09-16)

A fork of [cz-conventional-changelog](https://github.com/commitizen/cz-conventional-changelog).

Prompts for [conventional changelog](https://github.com/conventional-changelog/conventional-changelog) standard with an extra step to insert Jira ID. Jira ID is auto-detected from your branch name by default.

Jira ID in the format of /^[A-Z]+-[0-9]+\$/ will be automatically detected from the current branch name and be displayed as default at the prompt step. The step is optional so you can skip it if you do not have a Jira ID.

## Configuration

### package.json

Like commitizen, you specify the configuration of cz-conventional-changelog through the package.json's `config.commitizen` key.

```json5
{
// ...  default values
    "config": {
        "commitizen": {
            "path": "./node_modules/cz-conventional-changelog",
            "disableScopeLowerCase": false,
            "disableSubjectLowerCase": false,
            "maxHeaderWidth": 100,
            "maxLineWidth": 100,
            "defaultType": "",
            "defaultScope": "",
            "defaultSubject": "",
            "defaultBody": "",
            "defaultIssues": "",
            "types": {
              ...
              "feat": {
                "description": "A new feature",
                "title": "Features"
              },
              ...
            }
        }
    }
// ...
}
```

### Environment variables

The following environment varibles can be used to override any default configuration or package.json based configuration.

- CZ_TYPE = defaultType
- CZ_SCOPE = defaultScope
- CZ_SUBJECT = defaultSubject
- CZ_BODY = defaultBody
- CZ_MAX_HEADER_WIDTH = maxHeaderWidth
- CZ_MAX_LINE_WIDTH = maxLineWidth

### Commitlint

If using the [commitlint](https://github.com/conventional-changelog/commitlint) js library, the "maxHeaderWidth" configuration property will default to the configuration of the "header-max-length" rule instead of the hard coded value of 100. This can be ovewritten by setting the 'maxHeaderWidth' configuration in package.json or the CZ_MAX_HEADER_WIDTH environment variable.
