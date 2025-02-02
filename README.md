<h1>Firewall Configuration & Management</h1>


<h2>Description</h2>

This project focuses on configuring and managing the Uncomplicated Firewall (UFW) on Linux systems to enhance network security. It involves defining rules to allow or deny specific traffic based on ports, protocols, and IP addresses, such as permitting SSH access while blocking all other incoming traffic by default. Logging is enabled to monitor and analyze firewall activity, providing real-time insights and supporting forensic investigations. By streamlining rule management and integrating robust monitoring, this project demonstrates expertise in Linux security, scripting, and traffic control.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Bash</b> 
- <b>UFW (Uncomplicated Firewall)</b>
- <b>Journald</b>
- <b>Nmap</b>
   
<h2>Environments Used </h2>

- <b>Operating System: Kali Linux</b> (via VirtualBox on Windows 11 22H2)
- <b>Network Environment: Local network traffic analysis, utilizing Nmap scans from a separate machine to simulate various traffic patterns and test UFW rule enforcement.</b>
- <b>Development/Testing Tools: VirtualBox, PowerShell</b>

<h2>Program walk-through:</h2>

<p align="center">
The first step in configuring the UFW Firewall is to ensure the system is up-to-date. This is done by running sudo apt update to refresh the package list and sudo apt upgrade to install the latest updates. Keeping the system updated ensures compatibility and security for subsequent firewall configurations. : <br/>
<img src="https://i.imgur.com/HIirxt5.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
The next step is to install UFW using the package manager. Running sudo apt install ufw ensures the firewall utility is installed and ready for configuration. This step provides the foundational tool required to manage and enforce firewall rules effectively. :  <br/>
<img src="https://i.imgur.com/J5KzNAa.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
After installation, UFW is enabled by executing sudo ufw enable. This activates the firewall, applying the default rules to secure the system while allowing further customization for specific traffic management needs. : <br/>
<img src="https://i.imgur.com/176G82m.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
To ensure uninterrupted remote access, SSH connections are allowed by running sudo ufw allow ssh or sudo ufw allow 22. This rule permits traffic on port 22, preventing accidental lockout from the system during further firewall configuration. :  <br/>
<img src="https://i.imgur.com/EeJ91ob.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
Traffic rules are configured to permit necessary services and connections by allowing specific ports, port ranges, and services like HTTP and HTTPS. Rules are also set to allow traffic from particular IP addresses and subnets, ensuring controlled access to the system while maintaining security. These configurations are tailored to meet the specific requirements of the network environment. :  <br/>
<img src="https://i.imgur.com/9MmqiIX.png" height="80%" width="80%"
<br />
<img src="https://i.imgur.com/IC8UhIq.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
Firewall rules are configured to block unwanted traffic by denying specific ports, port ranges, and services. Additional rules restrict access from particular IP addresses and subnets to enhance security and prevent unauthorized connections. These denials ensure tighter control over network traffic and protect the system from potential threats. :  <br/>
<img src="https://i.imgur.com/0PLzAwW.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
The firewall's status and active rules are verified using sudo ufw status, with detailed information displayed using the verbose option. Numbered output simplifies rule management, allowing for easy identification and modification of specific rules. :  <br/>
<img src="https://i.imgur.com/qRTAujQ.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
Specific firewall rules are removed using sudo ufw delete, where the rule is identified from the numbered output. This ensures precise management and adjustment of the firewall's configuration as needed. :  <br/>
<img src="https://i.imgur.com/22a2Ue3.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
Logging is enabled with sudo ufw logging on to monitor firewall activity and track permitted or denied connections. Default policies are configured to allow all outgoing traffic and deny all incoming traffic, ensuring a secure baseline while permitting essential outbound communication. :  <br/>
<img src="https://i.imgur.com/qPqHBRY.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
The available application profiles are listed using sudo ufw app list, providing predefined configurations for common services. Nginx Full is allowed with sudo ufw allow 'Nginx Full', enabling HTTP and HTTPS traffic. This configuration is particularly beneficial in a home lab environment, facilitating web server setup and testing with secure and efficient traffic management. :  <br/>
<img src="https://i.imgur.com/KFrxUZG.png" height="80%" width="80%"
<br/>
<img src="https://i.imgur.com/lsToXr8.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
The UFW configuration is tested by performing an Nmap scan from another machine to check for open ports. This ensures that only the intended ports and services are accessible, verifying the effectiveness of the firewall rules in securing the system. :  <br/>
<img src="https://i.imgur.com/ItTi9J7.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
<br />
<br />
The effectiveness of UFW in blocking unauthorized traffic and allowing specific ports is verified by reviewing logs with journalctl. This analysis confirms that the firewall is functioning as intended, providing a clear record of permitted and denied connections. :  <br/>
<img src="https://i.imgur.com/fbiWlJC.png" height="80%" width="80%" alt="Firewall Configuration Steps"/>
</p>
