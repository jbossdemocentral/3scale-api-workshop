# Installation

## Installing 3scale API Workshop on OpenShift

This page describes the installation of the 3scale API Workshop from the latest sources from GitHub.

### Pre-requisites

To install the 3scale API Workshop, you need to have a host machine with the latest stable release version of the OpenShift client tools.

You can download the OpenShift Client Tools from [Red Hat Developers Portal Site](https://developers.redhat.com/products/openshift/download/) or follow the instructions on how to [Install the CLI](https://docs.openshift.com/container-platform/3.9/cli_reference/get_started_cli.html#installing-the-cli) from the openshift.com webpage.

You'll want to know how to [fork](https://help.github.com/articles/fork-a-repo/) and [clone](https://help.github.com/articles/cloning-a-repository/) a Git repository, and how to [check out a branch](https://git-scm.com/docs/git-checkout#git-checkout-emgitcheckoutemltbranchgt).

### Procedure

3scale API Workshop can be installed using automated Ansible playbooks or following the manual steps.

1. Git Clone the 3scale API Workshop repository:

    ```bash
    git clone https://github.com/hguerrero/3scale-api-workshop.git
    ```

1. Change to the project *install* folder:

    ```bash
    cd 3scale-api-workshop/support/install
    ```

### Installing using Ansible

We provide an Ansible playbook to install all the required components and software for this workshop.

Installing with Ansible requires creating an inventory file with the variables for configuring the system. Example inventory files can be found in the ansible/inventory folder. The following options are supported:

Name | Description | Default | Required
--- | --- | --- | ---
namespace | Namespace where 3scale API Management will be installed. | threescale | Yes, if *threescale* is enabled 
sso_project | Namespace where Red Hat Single Sign On will be installed. | rh-sso | Yes, if *sso* is enabled
apicurio_project | Namespace where Apicurio will be installed. | apicurio | Yes, if *apicurio* is enabled
gogs_project | Namespace where Gogs will be installed. | gogs | Yes, if *gogs* is enabled
microcks_project | Namespace where Microcks will be installed | microcks | Yes, if *microcks* is enabled
sso_version | The version tag used for getting the RH SSO templates. | ose-v1.4.9 | No
ocp_domain | Root domain of the OpenShift cluster. For example: `devday.openshiftworkshop.com` | | Yes
ocp\_apps\_domain | Root domain fpr the applications. For example: `apps.devday.openshiftworkshop.com`  | | Yes
usersno | Number of user tenants that will be created. | | Yes
threescale | Enable Red Hat 3scale API Management. | true | No
apicurio | Enable Apicurio Studio. | true | No
gogs | Enable Gogs Git Service. |  true | No
microcks | Enable Microcks. | true | No
sso | Enable Red Hat Single Sign On. | true | No
user_projects | | true | No
configure_only | Do not install the software, just configure existing installations. The software should be running in the same namespaces defined in the above vars. | false | No
create_tenants | Whether the workshop  should be installed in a multitenant mode or not. 3scale admin domains and developer portals for each of the users created during installation will be created. | true | Yes, if *threescale* is enabled
create_realms | If installing in multitenant mode, this will enable the creation of a RH SSO security realm for each one of the users created during installation. | true | No

An [example inventory](../support/ansible/inventory/workshop.inventory.example) that installs all the components in multitenant mode from the *bastion* machine looks like this:

```bash
[workshop]
localhost ansible_connection=local

[workshop:vars]
ocp_domain=apidays.openshiftoworkshop.com
ocp_apps_domain=apps.apidays.openshiftoworkshop.com
usersno=20
threescale=true
apicurio=true
gogs=true
microcks=true
sso=true
user_projects=true
configure_only=false
create_tenants=true
create_realms=true
```

1. Login to the OpenShift cluster.

    * If running on the cluster bastion become root:

      ```bash
      sudo su -
      ```

    * If running in an external client login as *opentlc-mgr* user:

      ```bash
      oc login -u opentlc-mgr https://[master-hostname] --insecure-skip-tls-verify
      ```
1. Run the Ansible playbook.

    ```bash
    ansible-playbook -i ansible/inventory/workshop.inventory ansible/playbooks/openshift/install.yml 
    ```

*If you install on OpenShift, it is required that you have cluster-admin access in order to set up the required roles for creating namespaces and managing resources in those namespaces*.
