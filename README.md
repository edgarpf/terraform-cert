# HashiCorp Certified: Terraform Associate
* ```volume_id   = aws_ebs_volume.data.id``` shows an implicit dependency.
* Removing a resource from Terraform management using the ```terraform state rm``` command ensures that the instance is not included in the resources to be destroyed when running ```terraform destroy```.
* Terraform requires a state file to store information about the current state of infrastructure resources.
* The correct additional parameter required to use multiple provider blocks of the same type with distinct configurations is the "alias" parameter.
* The two Terraform commands used to download and update modules are:
  * ```terraform init``: This command downloads and updates the required modules for the Terraform configuration. It also sets up the backend for state storage if specified in the configuration.
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
* 
