# CeProject.ops
This repository regroups the configuration-as-code to deploy [CeProject] on a dedicated VM.
CeProject is a deployment of the Open Source tool [OpenProject] for the CePro team at EPFL.
It uses [Ansible] wrapped in a [suitcase] called [`ceprojectsible`](./ceprojectsible).

## Prerequisites
- Access to the [Keybase] team `/keybase/team/ceproject/`
- Access to the prod VM (as root)

## How it works
`./ceprojectsible`
- Install some dependencies on the VM (Docker, docker-compose, Git, ...)
- Clone the git repository, copy the env variables from Keybase, run CeProject's containers

### Tags
- `ceproject.setup`
    - Install necessary dependencies on the VM
- `ceproject.run`
    - Clone the Git repository, and do the necessary to start the project : This is mostly what you want to do if you just made some changes to the project that you want to push in production.

To use a tag : `./ceprojectsible ceproject.setup`


[Ansible]: https://ansible.com/
[CeProject]: https://github.com/EPFL-CePro/CeProject/
[Keybase]: https://keybase.io/
[OpenProject]: https://openproject.org/
[suitcase]: https://github.com/epfl-si/ansible.suitcase/