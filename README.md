Testing
=======

`harness template:exec ./template.json --dest https://github.com/ldhertert/luke-testing-harness.git --var applicationName=Plex --var serviceName=ombi5`

todo
====

* Configuration/Secrets
* Logging
* Error handling
* Templating
* GraphQL
* Packaging
* Automated build
* Tests
* Move to harness github org
* Validation of user input
* In memory file system

harness-cli
===========

[![oclif](https://img.shields.io/badge/cli-oclif-brightgreen.svg)](https://oclif.io)
[![Version](https://img.shields.io/npm/v/harness-cli.svg)](https://npmjs.org/package/harness-cli)
[![Downloads/week](https://img.shields.io/npm/dw/harness-cli.svg)](https://npmjs.org/package/harness-cli)
[![License](https://img.shields.io/npm/l/harness-cli.svg)](https://github.com/ldhertert/harness-automation/blob/master/package.json)

<!-- toc -->
* [Usage](#usage)
* [Commands](#commands)
<!-- tocstop -->
# Usage
<!-- usage -->
```sh-session
$ npm install -g harness-cli
$ harness COMMAND
running command...
$ harness (-v|--version|version)
harness-cli/0.0.0 darwin-x64 node-v12.18.3
$ harness --help [COMMAND]
USAGE
  $ harness COMMAND
...
```
<!-- usagestop -->
# Commands
<!-- commands -->
* [`harness application:create NAME [DESCRIPTION]`](#harness-applicationcreate-name-description)
* [`harness application:delete NAMEORID`](#harness-applicationdelete-nameorid)
* [`harness application:update NAMEORID`](#harness-applicationupdate-nameorid)
* [`harness help [COMMAND]`](#harness-help-command)
* [`harness secrets:create NAME VALUE`](#harness-secretscreate-name-value)
* [`harness template:exec MANIFEST`](#harness-templateexec-manifest)

## `harness application:create NAME [DESCRIPTION]`

Create a new application

```
USAGE
  $ harness application:create NAME [DESCRIPTION]

ARGUMENTS
  NAME         The name of the application
  DESCRIPTION  A description of the application

OPTIONS
  --branch=branch              The branch name to use for git sync
  --gitConnector=gitConnector  The name or id of the git connector to use for git sync
  --syncEnabled                Whether or not git sync should be enabled
```

_See code: [src/commands/application/create.ts](https://github.com/ldhertert/harness-automation/blob/v0.0.0/src/commands/application/create.ts)_

## `harness application:delete NAMEORID`

Delete an application

```
USAGE
  $ harness application:delete NAMEORID

ARGUMENTS
  NAMEORID  The current name or id of the application
```

_See code: [src/commands/application/delete.ts](https://github.com/ldhertert/harness-automation/blob/v0.0.0/src/commands/application/delete.ts)_

## `harness application:update NAMEORID`

Update an application

```
USAGE
  $ harness application:update NAMEORID

ARGUMENTS
  NAMEORID  The current name or id of the application

OPTIONS
  --branch=branch              The branch name to use for git sync
  --description=description    The new description of the application. If omitted, the value will remain unchanged.
  --gitConnector=gitConnector  The name or id of the git connector to use for git sync
  --name=name                  The new name of the application.  If omitted, the value will remain unchanged.
  --syncEnabled                Whether or not git sync should be enabled. If omitted, the value will remain unchanged.
```

_See code: [src/commands/application/update.ts](https://github.com/ldhertert/harness-automation/blob/v0.0.0/src/commands/application/update.ts)_

## `harness help [COMMAND]`

display help for harness

```
USAGE
  $ harness help [COMMAND]

ARGUMENTS
  COMMAND  command to show help for

OPTIONS
  --all  see all commands in CLI
```

_See code: [@oclif/plugin-help](https://github.com/oclif/plugin-help/blob/v3.2.0/src/commands/help.ts)_

## `harness secrets:create NAME VALUE`

Create a new secret

```
USAGE
  $ harness secrets:create NAME VALUE

ARGUMENTS
  NAME   The name of the secret
  VALUE  The value of the secret

OPTIONS
  --accountScope
      Scope this secret to the account for use in delegate profiles

  --scope=scope
      [default: ALL_APPS::PROD_ENVS,ALL_APPS::NON_PROD_ENVS] 
      Restrict the use of this resource to specific Harness components.  
      The expected format is "application::environment".  
      The supported values for applications are "ALL_APPS", an application name, or an application id.  
      The supported values for environments are "PROD_ENVS", "NON_PROD_ENVS", an environment name, or an environment id.

      Examples:
      All applications, production environments: "ALL_APPS::PROD_ENVS"
      All applications, non-production environments: "ALL_APPS::NON_PROD_ENVS"
      Specific application, specific environment: "MyCoolApp::development"
      Specific application, non-production environment: "rPyC0kD_SbymffS26SC_GQ::nonprod"

  --type=(ENCRYPTED_TEXT)
      (required) [default: ENCRYPTED_TEXT]
```

_See code: [src/commands/secrets/create.ts](https://github.com/ldhertert/harness-automation/blob/v0.0.0/src/commands/secrets/create.ts)_

## `harness template:exec MANIFEST`

Apply steps defined in template manifest and send reults to target Harness account

```
USAGE
  $ harness template:exec MANIFEST

OPTIONS
  -v, --var=var
  --dest=dest          (required)
  --gitToken=gitToken  Token to use for git authentication
```

_See code: [src/commands/template/exec.ts](https://github.com/ldhertert/harness-automation/blob/v0.0.0/src/commands/template/exec.ts)_
<!-- commandsstop -->
