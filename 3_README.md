### What is a amazon machine image (AMI)
A machine image serves as a blueprint for creating virtual machine instances. It’s particularly useful for automating the creation of consistent machine images that can operate across various platforms.

### Packer vs Docker

Packer is an automated tool for building machine images for both containers and virtual machines. Images created with Packer can be deployed across various platforms, including Docker, and Amazon EC2. Packer utilizes "provisioners," or configuration tools, that allow for customization and flexibility in the image creation process. Packer utilizes builders, provisioners, and variables as primary configuration blocks within a Packer template.

Docker, on the other hand, is designed specifically for building, shipping, and running Docker containers. Docker images are built in layers. Packer lacks this layer-caching feature, making Docker faster for iterative builds within its ecosystem.

### Packer Commands

Packer is similar to Terraform in that executed commands search the current working directory for configuration files and it uses the command plus subcommand format to run. Here are some of the basic commands to get going:

`packer init` - intitializes packer plugins. This is similar to how Terraform intializes the configured providers
`packer validate` - validates packer configuration files. This is similar to Terraform’s validate subcommand and checks for syntax/configuration issues.
`packer build` - kicks off the packer build process. The build command is like running Terraform apply with the -auto-approve flag to bypass the user provided input.

### Components of a Packer Configuration File

The Packer configuration file consists of three main components:

1. **User Variables:** Defines parameters for the template to store secrets, environment variables, and other necessary settings.
2. **Builders:** Generates machine images. 
3. **Provisioners:** Install and configure software on the instance before the image is created. Provisioners are optional and include types such as Shell, Ansible, etc.
