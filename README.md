# HashiCorp Certified: Terraform Associate
* ```volume_id   = aws_ebs_volume.data.id``` shows an implicit dependency.
* Removing a resource from Terraform management using the ```terraform state rm``` command ensures that the instance is not included in the resources to be destroyed when running ```terraform destroy```.
* Terraform requires a state file to store information about the current state of infrastructure resources.
* The correct additional parameter required to use multiple provider blocks of the same type with distinct configurations is the "alias" parameter.
* The two Terraform commands used to download and update modules are:
  * ```terraform init```: This command downloads and updates the required modules for the Terraform configuration. It also sets up the backend for state storage if specified in the configuration.
  * ```terraform get```: This command is used to download and update modules for a Terraform configuration.
* The correct Terraform command to launch the Interactive console is "terraform console". This command allows users to evaluate and experiment with expressions in an interactive manner.
* ~>: Allows only the rightmost version component to increment.
* The private registry feature in Terraform Cloud allows users to publish and maintain custom modules within their organization, providing a secure and controlled environment for sharing infrastructure configurations.
* Terraform by default provisions 10 resources concurrently during a `terraform apply` command to speed up the provisioning process and reduce the overall time taken.
* Using ```terraform apply -replace=aws_instance.web``` allows you to mark a resource for replacement without affecting other resources that were created. This command is useful for quickly recreating a single resource.
* The `depends_on` argument in Terraform creates an explicit dependency between resources.
* Using Sentinel and OPA with Terraform Cloud provides several benefits that enhance the overall management and security of your infrastructure. Using Sentinel with Terraform Cloud provides a powerful mechanism to enforce policies, increase security, and maintain compliance in your infrastructure deployments. It gives you greater control and confidence in managing your cloud resources while promoting best practices and reducing the risk of misconfiguration.
* The correct environment variable to enable detailed logging for Terraform is `TF_LOG`. Setting this variable will provide detailed logs for troubleshooting and debugging purposes.
* The provider plugins are downloaded and stored in the `.terraform/providers` directory within the current working directory. This directory is specifically used by Terraform to manage provider plugins.
* The correct Terraform command to remove the lock on the state for the current configuration is `terraform force-unlock`.
* Using `terraform import` or the `import` block allows you to bring the existing resources under Terraform management without disrupting the availability of the deployed resources.
* The ```terraform validate``` command is used to check and report errors within modules, attribute names, and value types to ensure they are syntactically valid and internally consistent.
* Each Terraform workspace indeed uses its own state file to manage the infrastructure specific to that workspace.
* The terraform plan -refresh-only command is used in Terraform to update the state of your infrastructure in memory without making any actual changes to the infrastructure. The -refresh-only flag tells Terraform to only update its understanding of the current state of the infrastructure and not to make any changes.
* Terraform Community (Free) stores the local state for workspaces in a directory called `terraform.tfstate.d/`.
* HashiCorp recommends using 2 spaces between each nesting level in Terraform code for better readability and maintainability.
* The correct command to update the local name without replacing the existing resource is to use the `terraform state mv` command.
* The ```terraform show``` command is used to provide human-readable output from a state or plan file. This can be used to inspect a plan to ensure that the planned operations are expected, or to inspect the current state as Terraform sees it.
* Multiple providers can be declared within a single Terraform configuration file.
* Sentinel is an embedded policy-as-code framework integrated with the HashiCorp Enterprise products. It enables fine-grained, logic-based policy decisions, and can be extended to use information from external sources.
* If supported by your backend, Terraform will lock your state for all operations that could write state. This prevents others from acquiring the lock and potentially corrupting your state.
* API and CLI access are managed with API tokens, which can be generated in the Terraform Cloud UI.
* However, if you need even more detailed logging, you can set the TF_LOG environment variable to TRACE.
* ```terraform init -upgrade``` command perform update all previously installed plugins and modules to the newest version that complies with the configuration’s version constraints.
* To prevent a Terraform configuration from being executed if it contains a specific string, you can use Sentinel or Open Policy Agent (OPA) to enforce policy checks.
* The terraform apply -refresh-only command is used to reconcile the state Terraform knows about (via its state file) with the real-world infrastructure.
* Terraform is designed to work with almost any infrastructure that provides an API. Terraform is very frequently used to provision infrastructure atop VMware infrastructure, along with traditional, physical security or infrastructure service solutions.
* If the state has drifted from the last time Terraform ran,```terraform plan -refresh-only``` or ```terraform apply -refresh-only``` allows drift to be detected.
* If no explicit plan file is given on the command line, ```terraform apply``` will create a new plan automatically and prompt for approval to apply it.
* The optional -out flag can be used to save the generated plan to a file for later execution with ```terraform apply```, which can be useful when running Terraform in automation.
* Terraform Cloud agents are lightweight programs deployed within your target infrastructure environment. Their primary function is to receive Terraform plans from Terraform Cloud, execute those plans locally, and apply the desired infrastructure changes.
* Whenever a configuration's backend changes, you must run terraform init again to validate and configure the backend before you can perform any plans, applies, or state operations. Re-running init with an already-initialized backend will update the working directory to use the new backend settings. Either -reconfigure or -migrate-state must be supplied to update the backend configuration.
* Unlike many other objects in the Terraform language, a provider block may be omitted if its contents would otherwise be empty. Terraform assumes an empty default configuration for any provider that is not explicitly configured. In other words, if you don't have any specific configurations for your provider, you may indeed leave it out of your configuration.
* The ```terraform graph``` command is used to generate a visual representation of either a configuration or execution plan. 
* The ```terraform workspace show``` command is used to output the current workspace.
* A module that has been called by another module is often referred to as a child module.
* The ```terraform version``` command is used to display the currently installed version of Terraform on your system.
* The ```terraform login``` command can be used to automatically obtain and save an API token for Terraform Cloud, Terraform Enterprise, or any other host that offers Terraform services.
* The ```terraform output``` command in Terraform is used to display the values of outputs defined in the Terraform configuration.
