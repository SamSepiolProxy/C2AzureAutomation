# C2 Azure Automation

Automate deployment of Mythic or Covenant

Requires terraform and ansible to be installed.

Login with az login or use an azure sp account.

Configured to use the azure vm address.

### Deployment

python3 deploymentscript.py --deployment -w 127.0.0.1 -r C2Deployment

-r is the resource name

-w is the IP to be whitelisted to access the admin page and ssh port of the systems

### Provisioning

python3 deploymentscript.py --provision -w 127.0.0.1 -r C2Deployment -d jfjefnhsnfinc2rdr.uksouth.cloudapp.azure.com

### Destroying

python3 deploymentscript.py --destroy

### C2 Config

To deploy Covenant or Mythic change line 94 in deploymentscript.py to either:

covenant-setup.yaml

mythic-setup.yaml

![image](https://user-images.githubusercontent.com/57568210/140077921-19b16f13-3c93-4061-9de3-c29b2fb31df9.png)

#### Covenant

GruntHTTP will need adjusting\
Line 61\
ServicePointManager.SecurityProtocol = (SecurityProtocolType)3072 | SecurityProtocolType.Ssl3 | SecurityProtocolType.Tls;\
Line 858\
ServicePointManager.SecurityProtocol = (SecurityProtocolType)3072 | SecurityProtocolType.Ssl3 | SecurityProtocolType.Tls;


