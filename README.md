# Liquibase Init Project Action
Official GitHub Action to run Liquibase Init Project in your GitHub Action Workflow. For more information on how init project works visit the [Official Liquibase Documentation](https://docs.liquibase.com/commands/home.html).
## Init Project
Creates the directory and files needed to run Liquibase commands. Run without any flags on the CLI, or set via Environment variable, etc. will launch an interactive guide to walk users through setting up the necessary project's default and changelog files. This guide can be turned off by setting the 'liquibase.command.init.project.projectGuide=off'
## Usage
```yaml
steps:
- uses: actions/checkout@v3
- uses: liquibase-github-actions/init-project@v4.17.2
  with:
    # Relative or fully qualified path to the changelog file
    # string
    # Optional
    changelogFile: ""

    # Format of the project changelog sql|xml|json|yaml|yml
    # string
    # Optional
    format: ""

    # For remote project locations, do not delete temporary project files
    # bool
    # Optional
    keepTempFiles: ""

    # Password to use to connect to the database
    # string
    # Optional
    password: ""

    # File with default Liquibase properties
    # string
    # Optional
    projectDefaultsFile: ""

    # Relative or fully qualified path to the directory where the project files will be created
    # string
    # Optional
    projectDir: ""

    # Allow interactive prompts for init project
    # string
    # Optional
    projectGuide: ""

    # For remote project locations, recursive copy all project files to the remote location
    # bool
    # Optional
    recursive: ""

    # The JDBC database connection URL
    # string
    # Optional
    url: ""

    # Username to use to connect to the database
    # string
    # Optional
    username: ""

```

### Secrets
It is a good practice to protect your database credentials with [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## Optional Liquibase Global Inputs
The liquibase init project action accepts all valid liquibase global options as optional parameters. A full list is available in the official [Liquibase Documentation](https://docs.liquibase.com/parameters/command-parameters.html).

### Example
```yaml
steps:
  - uses: actions/checkout@v3
  - uses: liquibase-github-actions/init-project@v4.17.2
    with:
      headless: true
      licenseKey: ${{ secrets.LIQUIBASE_LICENSE_KEY }}
      logLevel: INFO
```

## Feedback and Issues
This action is automatically generated. Please submit all feedback and issues with the [generator repository](https://github.com/liquibase/github-action-generator/issues).
