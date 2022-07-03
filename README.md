# HashiCorp Certified: Terraform Associate
* You don't have to specify a provider block since Terraform is smart enough to download the right provider based on the specified resources.
* To upgrade an existing provider that you have already downloaded, you need to run ***terraform init -upgrade***.
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
* Terraform ***destroy*** will always prompt for confirmation before executing unless passed the -auto-approve flag.
* ***join("-", ["svr", "prd", "web"])*** will result in ***svr-prd-web***.
* ***lookup({a="hello", b="goodbye"}, "c", "what?")*** will result in "what?".
* You can use modules from a private registry, like the one provided by Terraform Cloud.
* Both the ***terraform get*** and ***terraform init*** commands will install and update modules. The ***terraform init*** command will also initialize backends and install plugins.
* It is important to consider that Terraform reads from data sources during the ***plan*** phase and writes the result into the plan.
* Terraform Enterprise offers the ability to use Terraform to deploy infrastructure in your local on-premises datacenter as well as a public cloud platform, such as AWS, Azure, or GCP.
* The constructs in the Terraform language can also be expressed in ***JSON*** syntax, which is harder for humans to read and edit but easier to generate and parse programmatically.
* By default, terraform init downloads plugins into a subdirectory of the working directory, .terraform/providers so that each working directory is self-contained.
* The Terraform language uses the following types for its values: string, number, bool, list (or tuple), map (or object. There are no other supported variable types in Terraform.
* A Terraform Enterprise install that is provisioned on a network that does not have Internet access is generally known as an ***air-gapped install***.
* Terraform can limit the number of concurrent operations as Terraform walks the graph using the ***-parallelism=n***  argument. The default value for this setting is ***10***. This setting might be helpful if you're running into API rate limits.
* Starting with Terraform 0.13 and above, ***terraform init*** can now automatically download community providers.
* The ***terraform workspace select*** command is used to choose a different workspace to use for further operations.
* The terraform state command is used for advanced state management. Rather than modify the state directly, the terraform state commands can be used in many cases instead.
* The ***terraform import*** command is used to import existing resources into Terraform. This allows you to take resources that you’ve created by some other means and bring them under Terraform management. Note that terraform import DOES NOT generate configuration, it only modifies state.
* ***tostring*** is not a string function, it is a type conversion function. ***tostring*** converts its argument to a string value.
* ***terraform force-unlock*** removes the lock on the state for the current configuration. Be very careful forcing an unlock, as it could cause data corruption and problems with your state file.
* An ***alias*** meta-argument is used when using the same provider with different configurations for different resources.
* The terraform apply -refresh-only command is used to reconcile the state Terraform knows about (via its state file) with the real-world infrastructure. This can be used to detect any drift from the last-known state, and to update the state file. This does not modify infrastructure but does modify the state file. If the state is changed, this may cause changes to occur during the next plan or apply.
* Single Sign-On, Sentinel and Audit Logging are NOT available in Terraform OSS or Terraform Cloud (free).
* The ***terraform validate*** command validates the configuration files in a directory, referring only to the configuration and not accessing any remote services such as remote state, provider APIs, etc.
* The ***terraform apply -replace*** command manually marks a Terraform-managed resource for replacement, forcing it to be destroyed and recreated on the apply execution.
You could also use ***terraform destroy -target virtual machine*** and destroy only the virtual machine and then run a terraform apply again.
* HashiCorp style conventions suggest you that align the equals sign for consecutive arguments for easing readability for configurations.
* Terraform analyzes any expressions within a resource block to find references to other objects and treats those references as implicit ordering requirements when creating, updating, or destroying resources.
* Modules also have output values, which are defined within the module with the output keyword. You can access them by referring to ***module.MODULE NAME.OUTPUT NAME***.
* Terraform has detailed logs that can be enabled by setting the ***TF_LOG*** environment variable to any value. This will cause detailed logs to appear on stderr.
* Each Terraform workspace uses its own state file to manage the infrastructure associated with that particular workspace.
* The ***terraform workspace new*** command is used to create a new workspace.
* There is no Terraform binary for Unix. Terraform is available for macOS, FreeBSD, OpenBSD, Linux, Solaris, Windows. 
* Currently, Terraform has no mechanism to redact or protect secrets that are returned via data sources, so secrets read via this provider will be persisted into the Terraform state, into any plan files, and in some cases in the console output produced while planning and applying. These artifacts must, therefore, all be protected accordingly.
* If you introduce a new provider Terraform needs to download the plugin to support the new resource that he has added. A terraform init will download the Infoblox plugin. Once that is complete, a plan and apply can be executed as needed.
* The ***depends_on*** argument is accepted by any resource and accepts a list of resources to create explicit dependencies for.
* If a resource is successfully created but fails during provisioning, Terraform will error and mark the resource as "tainted". A resource that is tainted has been physically created, but can't be considered safe to use since provisioning failed.
* You can use ***required_version*** to ensure that a user deploying infrastructure is using Terraform 0.12 or greater, due to the vast number of changes that were introduced. As a result, many previously written configurations had to be converted or rewritten.
* The ***terraform console*** command provides an interactive console for evaluating expressions.
* Provisioners are used to execute scripts on a local or remote machine as part of resource creation or destruction. Provisioners can be used to bootstrap a resource, cleanup before destroy, run configuration management, etc. Even if the functionality you need is not available in a provider today, HashiCorp suggests that you consider local-exec usage as a temporary workaround and to open an issue in the relevant provider's repo to discuss adding first-class support.
* The remote-exec provisioner invokes a script on a remote resource after it is created. The remote-exec provisioner supports both ssh and winrm type connections.
* A workspace can only be configured to a single VCS repo, however, multiple workspaces can use the same repo, if needed.
* The .gitignore file should be configured to ignore Terraform files that either contain sensitive data or aren't required to save. The terraform.tfstate file contains the terraform state of a specific environment and doesn't need to be preserved in a repo. The terraform.tfvars file may contain sensitive data, such as passwords or IP addresses of an environment that you may not want to share with others.
* ***TRACE*** is the most verbose and it is the default if ***TF_LOG*** is set to something other than a log level name.
* The Vault provider allows Terraform to read from, write to, and configure Hashicorp Vault.
* The prefix ***-/+*** means that Terraform will destroy and recreate the resource, rather than updating it in-place. Some attributes and resources can be updated in-place and are shown with the ***~*** prefix.
* Workspaces, managed with the terraform workspace command, isn't the same thing as Terraform Cloud's workspaces. Terraform Cloud workspaces act more like completely separate working directories.
* The ***terraform show*** command is used to provide human-readable output from a state or plan file. This can be used to inspect a plan to ensure that the planned operations are expected, or to inspect the current state as Terraform sees it.
* API and CLI access are managed with API tokens, which can be generated in the Terraform Cloud UI. Each user can generate any number of personal API tokens, which allow access with their own identity and permissions. Organizations and teams can also generate tokens for automating tasks that aren't tied to an individual user.
* 