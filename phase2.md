Phase 2 – SIEM Dashboard Analysis using Splunk on Kali
In this phase, we used Splunk on Kali Linux to analyze logs collected from the victim machine (Metasploitable3).
After multiple attempts to install and configure the Splunk Universal Forwarder on the victim, we encountered persistent compatibility errors due to the outdated operating system and unsupported architecture.
As a result, we decided to adopt a manual approach: log files were securely transferred using scp from the victim to the attacker machine (Kali), and then uploaded to Splunk for visualization and analysis.

Step 1: Install Splunk on Kali Linux
We downloaded and installed Splunk Enterprise on Kali Linux using the .deb package. After accepting the license and starting the service, we accessed the Splunk Web Interface at http://localhost:8000.
 
 
Step 2: Access Splunk Web Interface
We logged into Splunk Web Interface using the admin credentials set during the initial setup.
 
 
Step 3: Manually Uploading Log Files to Splunk
We used the `scp` command on Kali to copy the file `/home/vagrant/auth.log` from the victim (Metasploitable3) to our attacker machine.
Then, we used Splunk Web's `Add Data > Upload File` feature to ingest this file.
 
 

 
The log file was uploaded successfully to Splunk and is ready for searching and analysis.

Step 4: Search and Analyze Logs
We used the Splunk Search & Reporting app to analyze logins, failed authentications, and SSH behavior. This helped identify successful and failed login attempts from the attack.
 
 

Step 5: Dashboard Visualization
This spike in the graph indicates a significant increase in events related to unauthorized access attempts. The rise reflects the attacker's repeated login attempts on the SSH service, which were logged by the system.
 
