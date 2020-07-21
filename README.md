# Ansible on Azure

    1. Connect to Azure with Ansible

    <https://cloudskills.io/blog/connect-to-azure-with-ansible>

    2. Deploy a Windows Virtual Machine to Azure with Ansible

    <https://cloudskills.io/blog/deploy-ansible-azure>

    3. Connect to an Azure Windows Host with Ansible

    <https://cloudskills.io/blog/connect-ansible-windows>

    4. Configure a Windows Web Server with Ansible in Azure

    <https://cloudskills.io/blog/configure-ansible-windows>

## Run ansible playbook on Azure Cloud Shell

    ```
    az account list
    export AZURE_SUBSCRIPTION_ID=<your-subscription-id>
    ```

In the cloudshell

    ```
    code rg.yml
    ```

    ```YAML
    ---
    - hosts: localhost
    connection: local
    tasks:
        - name: Create resource group
        azure_rm_resourcegroup:
            name: ansible-rg
            location: eastus
        register: rg
        - debug:
            var: rg
    ```

Run the playbook

    ```
    ansible-playbook rg.yml
    ```


    ```
    ansible-playbook ./clouddrive/ansible-playbooks/deployWindowsAzureVirtualMachine.yaml
    ansible-playbook ./clouddrive/ansible-playbooks/configureAzureWinVmWinRM.yaml
    export USERPWDVAR="yourpasswordhere"
    ansible-playbook ./clouddrive/ansible-playbooks/configureWindowsVirtualServer.yaml -i <publiciphere>,
    ```
