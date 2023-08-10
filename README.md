# Doxygen Azure Blob Storage Deploy Action

GitHub Action for making and deploying Doxygen documentation to Azure Blob Storage

## Basic Usage

To deploy docs on every push to the `main` branch, create a new file in the `.github/workflows/` directory called `doxygen-azure-blob.yml` with the following contents:

```yml
name: Doxygen Azure Blob Storage Deploy Action

on:
  push:
    branches:
      - master

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: Born-Studios/doxygen-azure-blob-action@v1.3.2
        name: Uploading to Azure blob storage...
        with:
          azure_blob_connection_string: ${{ secrets.NPM_AUTH_TOKEN }}
```

## Options

- `azure_blob_connection_string` (required): Azure Access Keys Connection string.  [docs](https://learn.microsoft.com/en-gb/azure/storage/common/storage-account-keys-manage?tabs=azure-portal#regenerate-access-keys).
