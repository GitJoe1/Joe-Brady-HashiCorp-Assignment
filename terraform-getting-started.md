# Getting Started with Terraform Job Aid

Terraform is a popular tool for building, changing, and versioning infrastructure, a paradigm commonly known as infrastructure as code (IaC).

Terraform can manage existing and popular service providers, as well as custom in-house solutions.

Infrastructure is described using high-level configuration syntax. This allows a blueprint of your datacenter to be versioned and treated as you would any other code. Additionally, infrastructure can be shared and re-used.

Please visit [Install Terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli) to get detailed instructions on how to download the binary package for your environment.  
Please refer to this job aid for additional help with learner activities.  


After Terraform is installed, you can begin creating infrastructure.

We recommend creating a new directory on your local machine and a Terraform configuration inside it:

```shell
$ mkdir terraform-demo 
$ cd terraform-demo
```

Next, create a file for your Terraform configuration code:

```shell
$ touch main.tf
```

As an example, create a nginx Docker container.  Paste the following code into `main.tf`:

```hcl
terraform {
  required_providers {
    docker = {
      source = "kreuzwerker/docker"
    }
  }
}
provider "docker" {
    host = "unix:///var/run/docker.sock"
}
resource "docker_container" "nginx" {
  image = docker_image.nginx.latest
  name  = "training"
  ports {
    internal = 80
    external = 80
  }
}
resource "docker_image" "nginx" {
  name = "nginx:latest"
}
```

Initialize Terraform using the `init` command.

```shell
$ terraform init
```

Check for errors. If the command ran successfully, provision the resources with the `apply` command.

```shell
$ terraform apply
```

The command will take up to a few minutes to run and will display a message indicating that the resources were created.

Once satisfied with the results, destroy the infrastructure.

```shell
$ terraform destroy
```
