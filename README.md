<!-- start title -->

# GitHub Action:Buf generate

<!-- end title -->
<!-- start description -->

Uses Buf to generate compiled protos

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: Unsupervisedcom/action-buf-generate@undefined
  with:
    # Working directory
    # Default: ${{ github.workspace }}
    working-directory: ""
```

<!-- end usage -->
   <!-- start inputs -->

| **Input**               | **Description**   |        **Default**        | **Required** |
| :---------------------- | :---------------- | :-----------------------: | :----------: |
| **`working-directory`** | Working directory | `${{ github.workspace }}` |  **false**   |

<!-- end inputs -->
   <!-- start outputs -->

| **Output**      | **Description** | **Default** | **Required** |
| :-------------- | :-------------- | ----------- | ------------ |
| `random-number` | Random number   |             |              |

<!-- end outputs -->
   <!-- start examples -->

### Example usage with npm upload protos action, will result in an uploaded package called `@unsupervised/my-app`

```yaml
name: Build and upload npm protos to gar
on:
  release:
    types: [created]
jobs:
  build-upload-protos-npm:
    runs-on: ubuntu-latest
    steps:
      - uses: Unsupervisedcom/action-buf-generate@v1
      - uses: Unsupervisedcom/action-upload-protos-npm-gar@v1
        with:
          project-id: ${{ secrets.GOOGLE_ARTIFACT_PROJECT_ID }}
          credentials-json: ${{ secrets.GOOGLE_ARTIFACT_READ_WRITE }}
          package-name: "my-app"
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
