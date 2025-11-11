# Baserow Helm Repository

This repository contains Helm charts for deploying Baserow, an open-source no-code database platform, on Kubernetes clusters.

# Updating the Charts

This repository updates automatically on new Baserow releases. When triggered, the Baserow repository creates a Helm chart build and triggers the workflow in this repository. The workflow then downloads the built chart artifact and publishes it to GitHub Pages and the Artifact Hub registry.

## Setting Up GitHub App

To allow the Baserow repository to trigger updates in this chart repository, you need to create a GitHub App with the appropriate permissions.

For orgs: `https://github.com/organizations/<org-name>/settings/apps`
For personal: `https://github.com/settings/apps`

### Permissions Required

Select the following permissions when creating the GitHub App:

**Repository permissions**:
- **Contents**: `Read and write` (to trigger repository dispatch)
- **Actions**: `Read-only` (to download workflow artifacts)
- **Metadata**: `Read-only` (automatically selected)

### Set Up Repository Secrets and Variables

1. Create and copy the private key of the GitHub App
2. Copy the App ID
3. Install the application on both the **baserow** and **chart** repositories
4. Add these secrets and variables to the **baserow** and **chart** repositories:

   | Secret Name                  | Value                            | Description                         |
   | ---------------------------- | -------------------------------- | ----------------------------------- |
   | `CHART_REPO_APP_PRIVATE_KEY` | Full contents of the `.pem` file | Include BEGIN/END PRIVATE KEY lines |

   | Variable Name       | Value                         | Description                  |
   | ------------------- | ----------------------------- | ---------------------------- |
   | `CHART_REPO_APP_ID` | The App ID                    | Numeric ID of the GitHub App |
   | `CHART_REPO_OWNER`  | Your GitHub username/org name | e.g., `baserow` or `myorg`   |
   | `CHART_REPO_NAME`   | Chart repository name         | e.g., `baserow-chart`        |