# Send to API Action

This GitHub Action zips the files in your repository and sends the resulting ZIP file to PyScript.com. You must provide the project id (UUID) and the API key for authentication.

**WARNING**: This action will send the repository AS-IS to the project id - it will not replace files, instead it will overwrite them. Make sure you are sending the correct files to the correct project id.

## Inputs

- `api_token`: The API token for authentication. (required)
- `project_id`: The project ID to send the ZIP file to. (required)


## Example Usage

```yaml
name: Send to PyScript

on:
  push:
    branches:
      - main

jobs:
  send_files_job:
    runs-on: ubuntu-latest
    steps:
      - name: Send files to PyScript.com
        uses: FabioRosado/upload-to-pyscript@main
        with:
          api_token: ${{ secrets.PYSCRIPT_API_TOKEN }}
          projectid: '00000000-0000-0000-0000-000000000000'
```