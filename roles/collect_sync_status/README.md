# infra.aap_configuration.collect_sync_status

## Description

Ansible role that checks the status of synchronous tasks and optionally collects errors.

This is an internal role that is not meant to be called directly by users of this collection. It is the synchronous counterpart to `collect_async_status`, intended for use with modules implemented as action plugins where Ansible's async mechanism is not supported.

## Variables

|Variable Name|Default Value|Required|Description|
|:---|:---:|:---:|:---|
|`css_result`||yes|The result item from a synchronous looped task to check for errors|
|`css_error_list_var_name`||yes|The name of the dictionary key to use when collecting errors|
|`aap_configuration_collect_logs`|`false`|no|When enabled collects error messages and continues execution. Messages are collected in a variable called `aap_configuration_role_errors`|

### Secure Logging Variables

The following Variables complement each other.
If Both variables are not set, secure logging defaults to false.
The role defaults to false as normally the task does not include sensitive information.
`css_secure_logging` defaults to the value of `aap_configuration_secure_logging` if it is not explicitly called. This allows for secure logging to be toggled for the entire suite of configuration roles with a single variable, or for the user to selectively use it.

|Variable Name|Default Value|Required|Description|
|:---:|:---:|:---:|:---:|
|`aap_configuration_secure_logging`|`false`|no|This variable enables secure logging as well, but is shared across multiple roles, see above.|
|`css_secure_logging`|`false`|no|Whether or not to include the sensitive role tasks in the log. Set this value to `true` if you will be providing your sensitive values from elsewhere.|

## License

[GPLv3+](https://github.com/redhat-cop/infra.aap_configuration/blob/devel/LICENSE)

## Author

[Brant Evans](https://github.com/branic/)
