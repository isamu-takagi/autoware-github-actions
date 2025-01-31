# set-git-config

## Description

This action sets several git configs.

- `url.<base>.insteadOf`
- `user.name`
- `user.email`

## Usage

```yaml
jobs:
  example:
    runs-on: ubuntu-latest
    steps:
      - name: Generate token
        id: generate-token
        uses: tibdex/github-app-token@v1
        with:
          app_id: ${{ secrets.APP_ID }}
          private_key: ${{ secrets.PRIVATE_KEY }}

      - name: Set git config
        uses: autowarefoundation/autoware-github-actions/set-git-config@tier4/proposal
        with:
          token: ${{ steps.generate-token.outputs.token }}
```

## Inputs

| Name  | Required | Description                           |
| ----- | -------- | ------------------------------------- |
| token | true     | The token for `url.<base>.insteadOf`. |

## Outputs

None.
