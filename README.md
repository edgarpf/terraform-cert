# terraform-cert
Tips for HashiCorp Certified: Terraform Associate 

* You don't have to specify a provider block since Terraform is smart enough to download the right provider based on the specified resources.
* To upgrade an existing provider that you have already downloaded, you need to run ***terraform init -upgrade***
* Using ***terraform apply -replace*** is how you tag a resource for replacement. Useful in case Terraform reports that a resource was created but the local script did not run properly.
* Single Sign-On is a feature of Terraform Enterprise and Terraform Cloud for Business. It is NOT available in Terraform Cloud (free tier).
* State is a hard requirement for Terraform - there's no getting around it. You can have state stored locally or you can configure a remote backend to store it somewhere else. But overall, state is always required.
* Child modules can only access variables that are passed in the calling module block.
* State is used to map configuration to resources in the real world.
* Parallelism is the way Terraform can deploy many resources at the same time to speed up the deployment.
* Local variables are used to reduce repeating the same expressions or values over and over in your code.
* Resource blocks are the block type that deploys actual resources.
* The most secure place to store credentials when using a remote backend is outside of Terraform. Environment variables would be the second most-secure choice here.
* When plugins and modules are downloaded, they are stored under their respective directory in the .terraform folder within the current working directory.
* Private Module Registry helps you share Terraform providers and Terraform modules across your organization. It includes support for versioning, a searchable list of available providers and modules, and a configuration designer to help you build new workspaces faster.
* Sentinel runs before a configuration is applied, therefore potentially reducing cost for public cloud resources.
* State locking will lock your state for all operations that could write to the state file. It helps ensure only a single person can update or make changes to the resources Terraform is managing.
* You need to use ***TF_VAR_*** to set an environment variable for use with Terraform. For example ***TF_VAR_user***
* Using an enhanced storage backend allows you to execute your Terraform on infrastructure either locally or in Terraform Cloud.
* Terraform will store its state in the ***terraform.tfstate*** file on the local backend. This is the default but you can always change it if you want.
* A single configuration file can use multiple providers.
* Terraform can indeed manage dependencies across multiple cloud providers.
* In ***required_version = "~> 1.0.0"*** The ***~*** specifies that only the right-most version number can be incremented.
* The ***local-exec*** provisioner invokes a local executable after a resource is created. This invokes a process on the machine running Terraform, not on the resource.
* A terraform apply will run its own state refresh and see the configuration matches the deployed infrastructure in case of someone already created the resource specified in new code.
So, apply will do nothing.
* Terraform OSS does not support Sentinel, nor does the Free version of Terraform Cloud.
* You need to input variables that follow a key/value type structure. ***Map*** is the best choice for this use case because it allows you to create a key/value structure that can easily be referenced in your Terraform configuration.
* You need to run a ***terraform init*** first before any of these other commands will work.
* Trace is the most verbose logging level. In order, they go TRACE, DEBUG, INFO, WARN and ERROR.
* One of the functions that a terraform init does for you is download modules/plugins that can be used locally.
* To specify the version of Terraform provider that is required, you need to use the required_providers block parameter under the terraform block.
* While the value is not shown in the Terraform CLI output, the value will still be written to state. This is why it's important to secure your state file wherever possible.
* When a module is located at hashicorp/<name>, Terraform download it from the official Terraform pubic module registry.
* While it's not required, it is highly recommended to specify the version for each module to avoid issues with newer versions of the module that could break your configuration.
* You can delete a resource from state so Terraform no longer knows anything about it. Then you can run a terraform destroy to destroy the remaining resources.
To delete a resource from state, you can use the ***terraform state rm address command***, which will effectively make Terraform "forget" the object while it continues to exist in the remote system.
* Workspaces can be used to create separate state files for each regional deployment.
* Use ***terraform apply -refresh-only*** if an engineer makes a change outside of Terraform, what command can you run to detect drift and update the state file?
* Workspaces in OSS are often used within the same working directory while workspaces in Enterprise/Cloud are often (but not required) mapped to unique repos.
* A terraform apply will actually run its own "plan" to make sure it knows what resources to update.


