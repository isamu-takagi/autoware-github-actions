# get-self-packages

This action gets the list of ROS packages in the repository.

## Usage

```yaml
jobs:
  get-self-packages:
    runs-on: ubuntu-latest
    steps:
      - name: Check out repository
        uses: actions/checkout@v2

      - name: Get self packages
        id: get-self-packages
        uses: autowarefoundation/autoware-github-actions/get-self-packages@tier4/proposal
```

## Inputs

None.

## Outputs

| Name          | Description                                 |
| ------------- | ------------------------------------------- |
| self-packages | The list of ROS packages in the repository. |
