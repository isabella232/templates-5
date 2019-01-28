<p align="center">
  <a href="https://bitrise.io"><img src="https://raw.githubusercontent.com/trapacska/templates/master/assets/cli_logo.png" alt="Bitrise" width="888"></a>
</p>

<p align="center">
  <a href="/LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License"></img>
  </a>
  <a href="https://github.com/bitrise-io/bitrise/releases">
    <img src="https://img.shields.io/github/release/bitrise-io/bitrise.svg" alt="Latest Version"></img>
  </a>
  <a href="https://bitrise.io">
    <img src="https://app.bitrise.io/app/26f5d078435e58d7/status.svg?token=gZ40RNsW2ceVHbvDkvy7BQ&branch=master" alt="Latest Version"></img>
  </a>
</p>

<h4 align="center">Bitrise CLI is a Command Line Interface for running your Workflows and automate your local development processes (or almost anything) with a single terminal command. To see which steps you can use in your Workflows visit our <a href="https:/github.com/bitrise-io/bitrise-steplib">StepLib</a> or the <a href="https://app.bitrise.io/integrations">Integrations</a> page.
</h4>

<p align="center">
Some of our sub-sites if you are new to Bitrise and want read more about Workflows, Steps and our products:
<br>
  <a href="https://devcenter.bitrise.io">devcenter.bitrise.io</a> •
  <a href="https://discuss.bitrise.io">discuss.bitrise.io</a> •
  <a href="https://blog.bitrise.io">blog.bitrise.io</a>
</p>

---

<p align="center">
  <a href="https://bitrise.io">
    <img src="https://raw.githubusercontent.com/trapacska/templates/master/assets/bitrise_cli_loop.gif" alt="CLI in use" width="888"></img>
  </a>
<p>

# Feedback

Feel free to send us feedback on [Twitter](https://twitter.com/bitrise) or [file an issue](https://github.com/bitrise-io/bitrise/issues/new). Feature requests, pull requests are always welcome. If you wish to contribute, please take a quick look at the [Contribution](#contribution) section. If there's anything you'd like to chat about, please feel free to join our public [Slack](https://chat.bitrise.io/) workspace, or [Discuss](https://discuss.bitrise.io/) site.

# Install and Setup

#### Homebrew:
```sh
brew update && brew install bitrise
```

#### Pre-built binaries:

  [https://github.com/bitrise-io/bitrise/releases](https://github.com/bitrise-io/bitrise/releases) (Check a release for instructions)

#### From source (You'll need Go):
  ```
  go get -u github.com/bitrise-io/bitrise
  ```
  If you have `$GOPATH/bin` added to your `$PATH` then you can call `bitrise` instantly

#### To build from source

  ```
  git clone https://github.com/bitrise-io/bitrise.git $GOPATH/src/github.com/bitrise-io/bitrise
  cd $GOPATH/src/github.com/bitrise-io/bitrise
  go build
  ```
  Then you can call the built binary `./bitrise`.

>Optionally, you can call `bitrise setup` to verify that everything what's required for `bitrise` to run
is installed and available, but if you forget to do this it'll be performed the first
time you call `bitrise run`.

> Workflow shell completion for the `bitrise run` command:
[https://blog.bitrise.io/workflow-id-completion](https://blog.bitrise.io/workflow-id-completion)


# Usage

```txt
NAME: bitrise - Bitrise Automations Workflow Runner

USAGE: bitrise [OPTIONS] COMMAND/PLUGIN [arg...]

VERSION: 1.26.0

GLOBAL OPTIONS:
  --loglevel value, -l value  Log level (options: debug, info, warn, error, fatal, panic). [$LOGLEVEL]
  --debug                     If true it enabled DEBUG mode. If no separate Log Level is specified this will also set the loglevel to debug. [$DEBUG]
  --ci                        If true it indicates that we're used by another tool so don't require any user input! [$CI]
  --pr                        If true bitrise runs in pull request mode.
  --help, -h                  show help
  --version, -v               print the version

COMMANDS:
  init           Init bitrise config.
  setup          Setup the current host. Install every required tool to run Workflows.
  version        Prints the version
  validate       Validates a specified bitrise config.
  update         Updates the Bitrise CLI.
  run            Runs a specified Workflow.
  trigger-check  Prints out which workflow will triggered by specified pattern.
  trigger        Triggers a specified Workflow.
  export         Export the bitrise configuration.
  normalize      Normalize the bitrise configuration.
  step-list      List of available steps.
  step-info      Provides information (step ID, last version, given version) about specified step.
  workflows      List of available workflows in config.
  share          Publish your step.
  plugin         Plugin handling.
  stepman        Runs a stepman command.
  envman         Runs an envman command.
  help           Shows a list of commands or help for one command

PLUGINS:
  :analytics        Submitting anonymized usage information.
  :init             Initialize bitrise __config (bitrise.yml)__ and __secrets (.bitrise.secrets.yml)__ based on your project.
  :step             Manage Bitrise CLI steps
  :workflow-editor  Bitrise Workflow Editor.

COMMAND HELP: bitrise COMMAND --help/-h
```

<details><summary>Subcommands</summary>
<p>

<details><summary>init</summary>
<p>

    NAME:
    bitrise init - Init bitrise config.

    USAGE:
    bitrise init [command options] [arguments...]

    OPTIONS:
    --minimal  creates empty bitrise config and secrets
</p>
</details>

<details><summary>setup</summary>
    <p>

    NAME:
    bitrise setup - Setup the current host. Install every required tool to run Workflows.

    USAGE:
    bitrise setup [command options] [arguments...]

    OPTIONS:
    --full   Also calls 'brew doctor'.
    --clean  Removes bitrise's workdir before setup.
</p>
</details>
<details><summary>validate</summary>
    <p>

    NAME:
    bitrise validate - Validates a specified bitrise config.

    USAGE:
    bitrise validate [command options] [arguments...]

    OPTIONS:
    --path value, -p value       [Deprecated!!! Use 'config'] Path where the workflow config file is located.
    --config value, -c value     Path where the workflow config file is located.
    --config-base64 value   base64 decoded config data.
    --inventory value, -i value  Path of the inventory file.
    --inventory-base64 value     base64 decoded inventory data.
    --format value               Output format. Accepted: json, yml.
</p>
</details>
<details><summary>update</summary>
    <p>

    NAME:
    bitrise update - Updates the Bitrise CLI.

    USAGE:
    bitrise update [command options] [arguments...]

    OPTIONS:
    --version value  version to update - only for GitHub release page installations.
</p>
</details>
<details><summary>run</summary>
    <p>

    NAME:
    bitrise run - Runs a specified Workflow.

    USAGE:
    bitrise run [command options] [arguments...]

    OPTIONS:
    --workflow value        workflow id to run.
    --config value, -c value     Path where the workflow config file is located.
    --inventory value, -i value  Path of the inventory file.
    --secret-filtering     Hide secret values from the log.
    --json-params value   Specify command flags with json string-string hash.
    --json-params-base64 value   Specify command flags with base64 encoded json string-string hash.
    --path value, -p value       [Deprecated!!! Use 'config'] Path where the workflow config file is located.
    --config-base64 value   base64 encoded config data.
    --inventory-base64 value     base64 encoded inventory data.
</p>
</details>
<details><summary>trigger-check</summary>
    <p>

    NAME:
    bitrise trigger-check - Prints out which workflow will triggered by specified pattern.

    USAGE:
    bitrise trigger-check [command options] [arguments...]

    OPTIONS:
    --pattern value       trigger pattern.
    --config value, -c value     Path where the workflow config file is located.
    --inventory value, -i value  Path of the inventory file.
    --push-branch value   Git push branch name.
    --pr-source-branch value     Git pull request source branch name.
    --pr-target-branch value     Git pull request target branch name.
    --tag value   Git tag name.
    --format value        Output format. Accepted: json, yml.
    --json-params value   Specify command flags with json string-string hash.
    --json-params-base64 value   Specify command flags with base64 encoded json string-string hash.
    --path value, -p value       [Deprecated!!! Use 'config'] Path where the workflow config file is located.
    --config-base64 value   base64 encoded config data.
    --inventory-base64 value     base64 encoded inventory data.
</p>
</details>
<details><summary>trigger</summary>
    <p>

    NAME:
    bitrise trigger - Triggers a specified Workflow.

    USAGE:
    bitrise trigger [command options] [arguments...]

    OPTIONS:
    --pattern value       trigger pattern.
    --config value, -c value     Path where the workflow config file is located.
    --inventory value, -i value  Path of the inventory file.
    --secret-filtering     Hide secret values from the log. [$BITRISE_SECRET_FILTERING]
    --push-branch value   Git push branch name.
    --pr-source-branch value     Git pull request source branch name.
    --pr-target-branch value     Git pull request target branch name.
    --tag value   Git tag name.
    --json-params value   Specify command flags with json string-string hash.
    --json-params-base64 value   Specify command flags with base64 encoded json string-string hash.
    --path value, -p value       [Deprecated!!! Use 'config'] Path where the workflow config file is located.
    --config-base64 value   base64 encoded config data.
    --inventory-base64 value     base64 encoded inventory data.
</p>
</details>
<details><summary>export</summary>
    <p>

    NAME:
    bitrise export - Export the bitrise configuration.

    USAGE:
    bitrise export [command options] [arguments...]

    OPTIONS:
    --path value, -p value    [Deprecated!!! Use 'config'] Path where the workflow config file is located.
    --config value, -c value  Path where the workflow config file is located.
    --config-base64 value     base64 decoded config data.
    --format value      Output format. Accepted: json, yml.
    --outpath value    Output path, where the exported file will be saved.
    --pretty      Pretty printed export?
</p>
</details>
<details><summary>normalize</summary>
    <p>

    NAME:
    bitrise normalize - Normalize the bitrise configuration.

    USAGE:
    bitrise normalize [command options] [arguments...]

    OPTIONS:
    --path value, -p value    [Deprecated!!! Use 'config'] Path where the workflow config file is located.
    --config value, -c value  Path where the workflow config file is located.
    --config-base64 value     base64 decoded config data.
</p>
</details>
<details><summary>step-list</summary>
    <p>

    NAME:
    bitrise step-list - List of available steps.

    USAGE:
    bitrise step-list [command options] [arguments...]

    OPTIONS:
    --collection value, -c value  Collection of step. [$STEPMAN_COLLECTION]
    --format value  Output format. Accepted: json, yml.
</p>
</details>
<details><summary>step-info</summary>
    <p>

    NAME:
    bitrise step-info - Provides information (step ID, last version, given version) about specified step.

    USAGE:
    bitrise step-info [command options] [arguments...]

    OPTIONS:
    --collection value, -c value  Collection of step. [$STEPMAN_COLLECTION]
    --version value, -v value     Step version.
    --format value  Output format. Accepted: json, yml.
    --short       Show short version of infos.
    --step-yml value         Path of step.yml
</p>
</details>
<details><summary>workflows</summary>
    <p>

    NAME:
    bitrise workflows - List of available workflows in config.

    USAGE:
    bitrise workflows [command options] [arguments...]

    OPTIONS:
    --path value, -p value    [Deprecated!!! Use 'config'] Path where the workflow config file is located.
    --config value, -c value  Path where the workflow config file is located.
    --config-base64 value     base64 decoded config data.
    --format value      Output format. Accepted: raw, json.
    --minimal    Print summary of workflows only.
    --id-only    Print workflow ids only.
</p>
</details>
<details><summary>share</summary>
    <p>

    NAME:
    bitrise share - Publish your step.

    USAGE:
    bitrise share command [command options] [arguments...]

    COMMANDS:
        start   Preparations for publishing.
        create  Create your change - add it to your own copy of the collection.
        audit   Validates the step collection.
        finish  Finish up.

    OPTIONS:
    --help, -h  Show help.
</p>
</details>
<details><summary>plugin</summary>
    <p>

    NAME:
    bitrise plugin - Plugin handling.

    USAGE:
    bitrise plugin command [command options] [arguments...]

    COMMANDS:
        install  Install bitrise plugin.
        update   Update bitrise plugin. If <plugin_name> not specified, every plugin will be updated.
        delete   Delete bitrise plugin.
        info     Installed bitrise plugin's info
        list     List installed bitrise plugins.

    OPTIONS:
    --help, -h  Show help.
</p>
</details>
<details><summary>stepman</summary>
    <p>

    NAME:
    stepman - Step manager

    USAGE:
    stepman [global options] command [command options] [arguments...]

    VERSION:
    0.10.6

    COMMANDS:
        version      Prints the version
        setup   Initialize the specified collection, it's required before using a collection.
        update       Update the collection, if no --collection flag provided, all collections will updated.
        collections  List of localy available collections.
        step-list    List of available steps.
        step-info    Prints the step definition (step.yml content).
        download     Download the step with provided --id and --version, from specified --collection, into local step downloads cache. If no --version defined, the latest version of the step (latest found in the collection) will be downloaded into the cache.
        activate     Copy the step with specified --id, and --version, into provided path. If --version flag is not set, the latest version of the step will be used. If --copyyml flag is set, step.yml will be copied to the given path.
        audit   Validates Step or Step Collection.
        share   Publish your step.
        delete       Delete the specified collection from local caches.
        export-spec  Export the generated StepLib spec.
        help, h      Shows a list of commands or help for one command

    GLOBAL OPTIONS:
    --loglevel value, -l value  Log level (options: debug, info, warn, error, fatal, panic). (default: "info") [$LOGLEVEL]
    --help, -h    show help
    --version, -v         print the version
</p>
</details>
<details><summary>envman</summary>
    <p>

    NAME: envman - Environment variable manager

    USAGE: envman [OPTIONS] COMMAND [arg...]

    VERSION: 2.1.2

    GLOBAL OPTIONS:
    --loglevel value, -l value  Log level (options: debug, info, warn, error, fatal, panic). (default: "info") [$LOGLEVEL]
    --path value, -p value      Path of the envstore. [$ENVMAN_ENVSTORE_PATH]
    --tool, -t    If enabled, envman will NOT ask for user inputs. [$ENVMAN_TOOLMODE]
    --help, -h    Show help.
    --version, -v         Print the version.

    COMMANDS:
    version  Prints the version
    init     Create an empty .envstore.yml into the current working directory, or to the path specified by the --path flag.
    add      Add new, or update an exist environment variable.
    clear    Clear the envstore.
    print    Print out the environment variables in envstore.
    run      Run the specified command with the environment variables stored in the envstore.
    help     Shows a list of commands or help for one command

    COMMAND HELP: envman COMMAND --help/-h
</p>
</details>

</p>
</details>

# Contribution
- Fixing in source:
    - Fork this reporitory
    - Send in a PR with your changes
    - We will respond as soon as we can, if we requested any change then fix those
    - If we approve then it will be merged and your change will be released in the next CLI version

- Updating dependencies:
    > We have a built-in workflow for that, just call:
    ```sh
    bitrise run dep-update
    ```

- Building the source:

    After you forked this repository:

    ```
    git clone https://github.com/<your-github-name>/bitrise.git $GOPATH/src/github.com/bitrise-io/bitrise
    cd $GOPATH/src/github.com/bitrise-io/bitrise
    go build
    ```
    Then you can call the built binary `./bitrise`.
