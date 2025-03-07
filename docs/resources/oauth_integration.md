---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "snowflake_oauth_integration Resource - terraform-provider-snowflake"
subcategory: ""
description: |-
  
---

# snowflake_oauth_integration (Resource)



## Example Usage

```terraform
resource "snowflake_oauth_integration" "tableau_desktop" {
  name                         = "TABLEAU_DESKTOP"
  oauth_client                 = "TABLEAU_DESKTOP"
  enabled                      = true
  oauth_issue_refresh_tokens   = true
  oauth_refresh_token_validity = 3600
  blocked_roles_list           = ["SYSADMIN"]
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) Specifies the name of the OAuth integration. This name follows the rules for Object Identifiers. The name should be unique among security integrations in your account.
- `oauth_client` (String) Specifies the OAuth client type.

### Optional

- `blocked_roles_list` (Set of String) List of roles that a user cannot explicitly consent to using after authenticating. Do not include ACCOUNTADMIN, ORGADMIN or SECURITYADMIN as they are already implicitly enforced and will cause in-place updates.
- `comment` (String) Specifies a comment for the OAuth integration.
- `enabled` (Boolean) Specifies whether this OAuth integration is enabled or disabled.
- `oauth_client_type` (String) Specifies the type of client being registered. Snowflake supports both confidential and public clients.
- `oauth_issue_refresh_tokens` (Boolean) Specifies whether to allow the client to exchange a refresh token for an access token when the current access token has expired.
- `oauth_redirect_uri` (String) Specifies the client URI. After a user is authenticated, the web browser is redirected to this URI.
- `oauth_refresh_token_validity` (Number) Specifies how long refresh tokens should be valid (in seconds). OAUTH_ISSUE_REFRESH_TOKENS must be set to TRUE.
- `oauth_use_secondary_roles` (String) Specifies whether default secondary roles set in the user properties are activated by default in the session being opened.

### Read-Only

- `created_on` (String) Date and time when the OAuth integration was created.
- `id` (String) The ID of this resource.

## Import

Import is supported using the following syntax:

```shell
terraform import snowflake_oauth_integration.example name
```
