# Process of deploying an app

Various methods exist for deploying an application, and this section aims to familiarize you with diverse deployment approaches. It's worth noting that certain methods may offer quicker and more efficient deployment than others. The primary focus of this documentation is to highlight the automation procedures involved.

The order of presentation is organized from the highest level of interaction to the lowest:

1. [Manual Automation](manual.md)
- Manual automation refers to the process of automating tasks by actively guiding or executing them, often involving human intervention. It combines automated elements with manual steps for more control or adaptability.

2. [Automate install via Bash](automated.md)
- Automating installation via Bash involves using scripts to execute installation procedures without manual intervention, streamlining the process for efficiency and consistency. Bash scripts automate the sequential execution of commands for installing software dependencies or applications.

3. [Automate install via User Data](user_data.md)
- Automating installation via AWS user data involves leveraging cloud-init scripts to automate the setup and configuration of instances during their launch on AWS. This enables hands-free deployment by specifying custom scripts or commands to be executed at instance initialization, streamlining the installation process.
- Automating installation via [AMI](AMI)(Amazon Machine Image) involves making the deployment process faster and more efficient.

