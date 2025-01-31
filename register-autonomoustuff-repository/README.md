# register-autonomoustuff-repository

This action sets up the prerequisites for [pacmod3_msgs](https://github.com/astuff/pacmod3_msgs), which is used in Autoware.

> Note: This action assumes the caller workflow has installed `rosdep`.

## Usage

```yaml
jobs:
  build-and-test:
    runs-on: ubuntu-latest
    container: ros:galactic
    steps:
      - name: Check out repository
        uses: actions/checkout@v2

      - name: Register AutonomouStuff repository
        uses: autowarefoundation/autoware-github-actions/register-autonomoustuff-repository@tier4/proposal
        with:
          rosdistro: galactic

      - name: Get self packages
        id: get-self-packages
        uses: autowarefoundation/autoware-github-actions/get-self-packages@tier4/proposal

      - name: Build and test
        uses: autowarefoundation/autoware-github-actions/colcon-build-and-test@tier4/proposal
        with:
          rosdistro: galactic
          target-packages: ${{ steps.get-self-packages.outputs.self-packages }}
          build-depends-repos: build_depends.repos
```

## Inputs

| Name      | Required | Description     |
| --------- | -------- | --------------- |
| rosdistro | true     | The ROS distro. |

## Outputs

None.
