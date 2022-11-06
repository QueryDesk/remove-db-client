# Remove Database Client (QueryDesk)

Automate setting up a database client using https://querydesk.com so your 
team has instant access for debugging and testing.

This action allows you to cleanup connections that were previously created.

## Usage

```yaml
jobs:
  create_db:

    steps:
    # ...

    - name: Remove Database Client
      uses: QueryDesk/remove-db-client@v1
      with:
        api-key: ${{ secrets.QUERYDESK_API_KEY}}
        id: pr-${{ github.event.pull_request.number }} # your workflow trigger must be `pull_request` for this to work and must match the id passed on create

    # ...
```

## Inputs

-   `api-key`: (Required) You will need to create an API key on 
    https://app.querydesk.com/api-keys and save it as a secret in GitHub 
    Actions settings.
    
    Example API key:

    ```text
    SFMyNTY.g2gDbQAAAB5rZXlfMDFHSDRHWkFFVkVIOThCWlhXRzZFMjNOUlduBgDh2w9JhAFiAAFRgA.SeeINPdFn2cz6kqnkPb7IE7B9OLnc840R--hWiRoTYg
    ```

-   `id`: (Required) The id that was used to create the database connection.
