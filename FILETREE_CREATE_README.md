filetree_create
=============

**Getting started**
1. [infra.aap_configuration_extended.filetree_create](https://console.redhat.com/ansible/automation-hub/collections/validated/infra/aap_configuration_extended/documentation/role/filetree_create?version= "Documentation")<br>
2. [filetree_ee](https://quay.io/repository/zigfreed/filetree_ee "")<br>
3. [filetree EE.yml](https://github.com/ericcames/Execution-Environments/blob/main/filetree_ee/execution-environment.yml "")<br>
4. Build your own filetree_ee - Optional
```
mkdir filetree_ee
cd filetree_ee
touch execution-environment.yml
vi execution-environment.yml
ansible-builder build -v3 -t filetree_ee:1.0.0
podman images
podman tag localhost/filetree_ee:1.0.0 quay.io/zigfreed/filetree_ee:1.0.0
podman login quay.io
podman push quay.io/zigfreed/filetree_ee:1.0.0

We can do the same with Private Automation Hub!
```
5. Add the ee in the platform
    - Name
    ```
    filetree_ee
    ```
    - Image
    ```
    quay.io/zigfreed/filetree_ee:latest
    ```
    - Pull
    ```
    Only pull the image if not present before running
    ```

6. Create a job template in the platform
    - Name
    ```
    filetree_ee
    ```
    - Inventory
    ```
    Demo Inventory
    ```
    - Project
    ```
    aap.as.code.starter.kit
    ```
    - Execution environment
    ```
    filetree_ee
    ```
    - Playbook
    ```
    playbooks/filetree_create.yml
    ```
    - Credentials
    ```
    AAP Credential
    ```
    - Create a survey for your software repo token
    - Name
    ```
    Repo Token
    ```
    - Type
    ```
    password
    ```
    - Default
    ```
    TOKEN HERE
    ```
    - Survey Enabled