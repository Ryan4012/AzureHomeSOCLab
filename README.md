<h1>Azure Home SOC Lab</h1>


<h2>Description</h2>
To begin this lab, I created a resource group named RG-SOC-Lab, setting the region to East US 2. This resource group serves as the container for all components of the SOC (Security Operations Center) lab. Next, I set up a virtual network named Vnet-soc-lab within the same resource group to manage networking for our lab environment. Following this, I created a Virtual Machine named CORP-NET-EAST-2, running Windows 10 Pro. During configuration, I modified the Inbound Security Rules by removing the default RDP (Remote Desktop Protocol) rule and replacing it with a custom rule that allows all inbound traffic. This configuration intentionally increases the virtual machine's vulnerability, simulating a more realistic attack surface for monitoring purposes. After configuring the VM, I logged in and disabled all Windows Firewall settings to further expose the system to potential threats. I then verified internet connectivity by pinging the VM’s public IP address from my local machine using the Command Prompt. With the VM running and accessible, I proceeded to create a Log Analytics Workspace named LAW-soc-lab. This workspace allows us to write and run custom queries to monitor specific event logs and activity. To extend monitoring capabilities, I enabled Microsoft Sentinel and linked it to the LAW-soc-lab workspace. Within Sentinel, I added the Windows Security Events data connector and used the Azure Monitor Agent (AMA) to connect the Virtual Machine to the workspace. This completes the core setup of the SOC lab, laying the groundwork for active threat detection, event monitoring, and alert generation using Microsoft Sentinel.

<br />[View SOC Lab Attack Map](https://portal.azure.com/#blade/AppInsightsExtension/WorkbookViewerBlade/ComponentId/%2Fsubscriptions%2F1793b41d-6d3d-4b8e-94c8-26d8b855601e%2Fresourcegroups%2Frg-soc-lab%2Fproviders%2Fmicrosoft.operationalinsights%2Fworkspaces%2Flaw-soc-lab/ConfigurationId/%2Fsubscriptions%2F1793b41d-6d3d-4b8e-94c8-26d8b855601e%2Fresourcegroups%2Frg-soc-lab%2Fproviders%2Fmicrosoft.insights%2Fworkbooks%2F353e9330-2228-4430-b68f-55b17ceef01e/Type/sentinel/WorkbookTemplateName/Windows%20VM%20Attack%20Map) (For a more interactive view)
<br />

<h2>Languages and Utilities Used</h2>

- <b>Kusto Query Language (KQL)</b> 
- <b>Log Analytics Workspace</b>

<h2>Environments Used </h2>

- <b>Azure Cloud Services</b>
- <b>Azure Virtual Machine</b>
- <b>Microsoft Sentinel</b>

<h2>Project walk-through:</h2>

<p align="center">
SOC Lab Attack map after 24 hours: <br/>
<img src="https://i.imgur.com/XfTSBU4.png" height="100%" width="100%" alt="SOC"/>
<br />
<br />

</p>
