# Action BI Toolkit | pbi-tools Deployment Demo

Using `pbi-tools deploy` with Azure Pipelines.

## Setup

* [Environments](https://dev.azure.com/pbitools/pbi-tools%20Report%20Demo/_environments): "1_Development", "2_Staging", "3_Production"
* [Pipeline YAML File](./azure-pipelines.yml)
* `PBI_CLIENT_SECRET` pipeline variable (secret)
* [pbi-tool Deployment Manifest](./.pbixproj.json)
* Three target Power BI Workspaces
  * [pbi-tools Demo [Dev]](https://app.powerbi.com/groups/82d08e54-8dd8-4af1-84fd-013c008f695d)
  * [pbi-tools Demo [Staging]](https://app.powerbi.com/groups/9f2032e9-6189-4f45-83a7-d9b15b8709d4)
  * [pbi-tools Demo [Production]](https://app.powerbi.com/groups/67ec2e2c-daf7-4def-8bab-fbdbb1212587)
  * [Shared Power BI Dataset](https://app.powerbi.com/groups/313d6b68-aa84-4ba5-b65b-53d0e8889489/datasets/cb8781bc-11f4-42a7-b6b6-53e9a8e8adcb/details)

## Branching Model

This deployment demo implements a branching strategy in which specific branches are linked to environments. Deployments are triggered when changes are pushed into the respective branches.

| Branch Pattern | Environment | Workspace |
| --- | --- | --- |
| `Release/*` | 1_Development | [pbi-tools Demo [Dev]](https://app.powerbi.com/groups/82d08e54-8dd8-4af1-84fd-013c008f695d) |
| `uat` | 2_Staging | [pbi-tools Demo [Staging]](https://app.powerbi.com/groups/9f2032e9-6189-4f45-83a7-d9b15b8709d4) |
| `main` | 3_Production | [pbi-tools Demo [Production]](https://app.powerbi.com/groups/67ec2e2c-daf7-4def-8bab-fbdbb1212587) |
