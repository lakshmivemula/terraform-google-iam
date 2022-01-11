# Module bigquery_datasets IAM

This submodule is used to assign BigQuery dataset roles.

## Example Usage
```
module "bigquery_metadataViewer" {
source = "github.com/lakshmivemula/terraform-google-iam.git//modules/bigquery_datasets_iam/“
bigquery_datasets  = ["my_big_query_one", "my_bigquery_dataset_two"]


  project = var.project
  role    = "roles/bigquery.dataViewer"
  members = [
    "user:akhusimi@gmail.com",
    
  ]
}
```

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| bigquery\_datasets | BigQuery dataset IDs list to add the IAM policies/bindings | `list(string)` | n/a | yes |
| bindings | Map of role (key) and list of members (value) to add the IAM policies/bindings | `map(any)` | n/a | yes |
| mode | Mode for adding the IAM policies/bindings, additive and authoritative | `string` | `"additive"` | no |
| project | Project to add the IAM policies/bindings | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| bigquery\_datasets | Bigquery dataset IDs which received for bindings. |
| members | Members which were bound to the bigquery datasets. |
| roles | Roles which were assigned to members. |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
