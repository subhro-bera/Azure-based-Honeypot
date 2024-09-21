Azure Based - Honeypot Creation : Cloud Native Honeypot and Microsoft Sentinel Analysis

* Create a free Azure Trial Account to use few resources

    * Process:

        * Step 1: Create a New Virtual Machine: HoneypotVM
            * Note we need RDP or SSH as per OS installed : Inbound port rules: Allow
            * Selected Port : As per OS (RDP for Windows or SSH for Linux)

        * Step2: Make the VM Vulnerable (Intentionally)
            * Turn off the VM’s Firewall: For windows -> Windows Defender Firewall -> Turn Off OR For Linux disable the firewall or UFW (mycase) using appropriate commands based on the distro.
            * Open all ports-> VM’s “Networking” settings-> Add inbound port rules to open more ports, mimicking a poorly secured or configured machine.

        * Step 3: Setting Up Log Analytics for a Honeypot
            * Create a new workspace under Log Analytics Dashboard
            * Connect Your VM to Log Analytics
            * Install the Log Analytics agent on your VM
            * For Windows, download and install the agent directly from the Log Analytics workspace instructions.
            * For Linux, follow the command-line instructions provided in the Log Analytics workspace
            * Configure the VM to send log data to the workspace you created.

        * Step 4: Logging and Monitoring with Azure Sentinel
            * Azure Sentinel-> Create and link Log Analytics Workspace created earlier

        * Step 5: Analyzing Cyber Attacks with PowerShell and Microsoft Remote Desktop on MacBook
            * Connect to Your VM: We need IP address to be extracted via Microsoft Remote Desktop to connect to created honeypot VM.
            * I used a powershell script to extract IP address from windows event logs from the Honeypot windows based OS event viewer
            * We need a Geolocation API which would allow us to extract the iP location wherever the request is coming from.

        * Step 6: Integrating Azure Sentinel for Advanced Security Analysis:
            * Connect Data Sources
            * Set Up Detection Rules and Playbooks
            * Visualizing Attacks: Creating a Cyber Threat Landscape Map : PowerShell scripts, visualize the origins of cyber-attacks on a world map within Azure Sentinel.
