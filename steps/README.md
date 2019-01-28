# Flutter Build

> This step will build a Flutter project

## Inputs

- project_location: "$BITRISE_SOURCE_DIR" __(required)__ __(sensitive)__
    > The root dir of your Flutter project
- android_additional_params: "--release" __(sensitive)__
    > The flags from this input field will be appended to the `flutter build apk` command.
- android_output_pattern: "*build/app/outputs/apk/*/*.apk"
    > Pattern to find built artifacts relative to $BITRISE_SOURCE_DIR
  #### Android Platform Configs
    - android_additional_params: "--release" __(sensitive)__
        > The flags from this input field will be appended to the `flutter build apk` command.
    - android_output_pattern: "*build/app/outputs/apk/*/*.apk"
        > Pattern to find built artifacts relative to $BITRISE_SOURCE_DIR
  #### iOS Platform Configs
    - ios_additional_params: "--release" __(sensitive)__
        > The flags from this input field will be appended to the `flutter build apk` command.
    - ios_output_pattern: "*build/app/outputs/apk/*/*.apk"
        > Pattern to find built artifacts relative to $BITRISE_SOURCE_DIR

## Outputs

- BITRISE_APK_PATH: The created .apk file's path
    > Description if any
- BITRISE_APK_PATH_LIST: Another title here
- ANOTHER_SAMPLE_ENV: Another title here

## Contribute

1. Fork this repository
1. Make changes
1. Send a PR to our team

## How to run this step

#### Using Bitrise CLI

1. Clone this repository
1. `cd` to the cloned repository's root
1. Create a bitrise.yml (if not yet created)
1. Prepare a workflow that contains a step with the id: `path::./`
    > For example:
    > ```yaml
    > format_version: "6"
    > default_step_lib_source: https://github.com/bitrise-io/bitrise-steplib.git
    > 
    > workflows:
    >   my-workflow:
    >     steps:
    >     - path::./:
    >         inputs: 
    >         - my_input: "my input value"
    > ```
1. Run the workflow: `bitrise run my-workflow`

#### Running from terminal

- If the step uses Go toolkit:
    - Clone this repository _(if the Step is Go based then clone under the package's GOPATH for example: $GOPATH/src/github.com/bitrise-steplib/bitrise-step-flutter-build)_
    - `cd` to the cloned repository's root
    - Run `go run *.go` and set the inputs from the `step.yml` as envs for the command
        > For example:
        > ```sh
        > example_step_input="my custom step input" go run *.go
        > ```

- If the step uses Bash toolkit:
    - Clone this repository
    - `cd` to the cloned repository's root
    - Run `./step.sh` and set the inputs from the `step.yml` as envs for the command
        > For example:
        > ```sh
        > example_step_input="my custom step input" ./step.sh
        > ```


## About
This is an official Step managed by Bitrise.io and is available in the [Workflow Editor](https://www.bitrise.io/features/workflow-editor) and in our [Bitrise CLI](https://github.com/bitrise-io/bitrise) tool. If you seen something in this readme that never before please visit some of our knowledge base to read more about that:
  - devcenter.bitrise.io
  - discuss.bitrise.io
  - blog.bitrise.io
