# Provisioning of an Azure VM with terraform 

The main idea of this project is to provision and deploy a remote web development environment in Azure cloud available via secure tunneling, with terraform as the IaaS tool, and VS code CLI as the code editor inside the remote machine. All is based on the [FreeCodeCamp video][1] that is shown at the end of this file, the changes made where to eliminate the need to use SSH, by enabling the secure tunneling when the machine is deployed eliminating the need to log in the remote via SSH to activate the secure tunnel, allowing the user to only use its github credentials on any visual Studio code instance to use their remote environment. 

## Project Diagram

![Diagrama_Terraform_AZ](https://github.com/Shmuel0/terraform-azure/assets/116227651/44fceb77-290d-473d-bae2-ab2c2f2d764e)


## Notes

The windows ssh script file is not necessary but it is a great way for the hostname and public ip to be sent from the VM to the PC where you have the azure credentials and terraform cli installed, it allows to connect from your personal and secure pc to de VM, without the need of authenticating with github. ON YOUR PERSONAL MACHINE. 

The customdata handles the dependancies that you need on the vm, for example here is added docker just as in the video because I didn't need more dependancies at the moment of release. This procedure of keeping the applications and dependancies up to date and managing the configuration it's better suited for Ansible but for first deployments Terraform is a better option thanks to it's comprenhensive approach of provissioning using cloud providers APIs. 

Basically according to [SpaceLift][2], if we identify Orchestration as Day 0 activity and configuration management as Day 1 activity. Terraform works best for Day 0 activities and Ansible for Day 1 and onwards activities.

[1]: https://www.youtube.com/watch?v=V53AHWun17s&t=193s&pp=ygUiZnJlZWNvZGVjYW1wIGF6dXJlIGRldiBlbnZpcm9ubWVudA%3D%3D  "FreeCodeCamp video"
[2]: https://spacelift.io/blog/ansible-vs-terraform  "SpaceLift"
