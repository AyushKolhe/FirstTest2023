Different OS - linux, windows
commands on linux
what is tomcat
what is nginx
what are APIs used for.

Tools:
Jenkins
azure devops
IDE - IntelliJ, Visual Studio

15-Dec-23
TO DO
- what is route53
- what is Dns, cname, A record
load balancer in aws and different types of load balancers
- what are target hosts
- what is nslookup used for: Nslookup is the name of a program that lets users enter a host name and find out the corresponding IP address or domain name system (DNS) record. Users can also enter a command in nslookup to do a reverse DNS lookup and find the host name for a specified IP address.
Network administrators use nslookup to troubleshoot server connections or for security reasons. For example, network pros might use nslookup to guard against phishing attacks, in which attackers alter domain names. An attacker might substitute the numeral 1 for a lowercase l to make an unfriendly site look friendly and familiar, e.g., joes1owerprices.com vs. joeslowerprices.com. Network admins use nslookup to troubleshoot such attacks.

DNS, or nslookup, also helps deter cache poisoning, in which attackers distribute data to caching resolvers that pose as authoritative origin serve


- difference between http and https :Hypertext transfer protocol (HTTP) is a protocol or set of communication rules for client-server communication. When you visit a website, your browser sends a HTTP request to the web server, which responds with an HTTP response. The web server and your browser exchange data as plaintext. In short, HTTP protocol is the underlying technology that powers network communication. As the name suggests, hypertext transfer protocol secure (HTTPS) is a more secure version or an extension of HTTP. In HTTPS, the browser and server establish a secure, encrypted connection before transferring data.

 HTTP transmits unencrypted data, which means that information sent from a browser can be intercepted and read by third parties. This wasn’t an ideal process, so it was extended into HTTPS to add another layer of security to communication. HTTPS combines HTTP requests and responses with SSL and TLS technology.

HTTPS websites must obtain an SSL/TLS certificate from an independent certificate authority (CA). These websites share the certificate with the browser before exchanging data to establish trust. The SSL certificate also contains cryptographic information, so the server and web browsers can exchange encrypted or scrambled data. The process works like this:

You visit an HTTPS website by typing the https:// URL format in your browser’s address bar.
The browser attempts to verify the site’s authenticity by requesting the server’s SSL certificate.
The server sends the SSL certificate that contains a public key as a reply.
The website’s SSL certificate proves the server identity. Once the browser is satisfied, it uses the public key to encrypt and send a message that contains a secret session key.
The web server uses its private key to decrypt the message and retrieve the session key. It then encrypts the session key and sends an acknowledgment message to the browser.
Now, both browser and web server switch to using the same session key to exchange messages safely.




- paramter store vs secret manager aws  :
- AWS gives you two ways to store and manage application configuration data centrally:

Secrets Manager: It was designed specifically for confidential information (like database credentials, API keys) that needs to be encrypted, so the creation of a secret entry has encryption enabled by default. It also gives additional functionality like rotation of keys.
Systems Manager Parameter Store: It was designed to cater to a wider use case, not just secrets or passwords, but also application configuration variables like URLs, Custom settings, AMI IDs, License keys, etc.
Similarities
Encryption
Both Secrets Manager and Parameter Store can leverage AWS KMS to encrypt values. By using KMS, IAM policies can be configured to control permissions on which IAM users and roles have permission to decrypt the value. Though access to the values can be restricted through IAM, encryption provides an additional layer of security and is sometimes required for compliance.

Key/Value Store
Both services allow you to store values under a name or key.
Both allow the keys to having prefixes. For example, parameters or secrets can be put in the following prefix schema application/environment/parametername or any other combination of prefixes that meets the need of the application. This is useful since the deployment of the application can reference different parameters/secrets based on the deployment environment.

CloudFormation Integration
CloudFormation is used as an Infrastructure as a code (IaC) model, and storing secrets in CloudFormation is a bad security practice. You can store the secrets (e.g. Database username and password) in Parameter Store or Secrets Manager which can be referenced in the CloudFormation template so that you just have a pointer to the value in your template instead of containing the secrets in plaintext.

Versioning
Both services support versioning of secret values. This allows you to view previous versions of your parameters of secret in case you needed them. You can choose to restore the older version of the parameter.
Parameter Store only allows one version of the parameter to be active at any given time.
Secrets Manager allows multiple versions to exist at the same time when you are performing a secret rotation using the staging labels.

Key Differences
Cost
Secrets Manager: It is paid. The storage cost is $0.40 per secret per month and API interactions cost is $0.05 per 10,000 API calls.

Parameter Store: For Standard parameters, No additional charge for storage and standard throughput. For higher throughput, API interactions cost is $0.05 per 10,000 API calls.
For Advanced parameters, storage cost is $0.05 per advanced parameter per month and API interactions cost is $0.05 per 10,000 API calls.

Secrets Rotation
Secrets Manager: It offers the ability to switch secrets at any given time and can be configured to regularly rotate depending on your requirements. It provides full key rotation integration with few AWS service like RDS, Redshift, DocumentDB. For other services, AWS allows you to write custom key rotation logic using an AWS Lambda function.

Parameter Store: You can write your own function that updates credentials managed by Parameter Store, and invoking it via a CloudWatch scheduled event or Eventbridge.

Cross-account Access
Secrets Manager: Secrets can be accessed from another AWS account. It easier to share the secrets cross-accounts. This is useful if secrets are centrally managed from another AWS account or beneficial for use cases where a customer needs to share a particular secret with a partner.

Parameter Store: Not supported.

Secret Size
Secrets Manager: It can store up to 10KB secret size.

Parameter Store: Standard Parameters can store up to 4096 characters (4KB size) for each entry, and Advanced Parameters can store up to 8KB entries.

Limits
Secrets Manager: It has a limitation of storing 500,000 secrets per region per account.

Parameter Store: It has a limitation of storing 10,000 standard parameters per region per account.

Multiple Regions Replication
Secrets Manager: It lets you easily replicate your secrets in multiple AWS Regions to support applications spread across those Regions as well as disaster recovery scenarios.

Parameter Store: It doesn’t support cross region replication out of the box.

Use Cases
Choose Secrets Manager if:
You want to store only encrypted values and super easy way to manage the rotation of the secrets. For instance, for organizations that have to be PCI compliant where the mandate is to rotate your passwords every 90d, AWS Secrets Manager makes that a very easy and seamless process.
Choose Parameter Store if:
You want cheaper option to store encrypted or unencrypted secrets.
Alternatives
Hashicorp Vault
Azure Key Vault
Azure App Configuration
Summary
Parameter Store can be used to store the secrets encrypted or unencrypted fashion. It helps you optimize and streamline application deployments by storing environmental config data, other parameters and it is free. AWS Secrets Manager takes it up by few notches by providing additional functionality such as rotation of keys, cross-account access and tighter integration with AWS services.

Recommendation: Use Secrets Manager to store confidential secrets like database credentials, API keys, OAuth tokens. Use Parameter Store to store other application settings, environmental config data, License codes, etc.

Prefer storing secrets in Secrets Manager or Parameter Store instead of storing them in a config file or hard-coded in applications.



- nginx vs tomcat : Tomcat is an application server and NGINX is a web server.


- Deploy a war file in tomcat and try to access using http url on the EC2.
- Ansible and helm pacakage manager
- python atleast boto aws simple programs
- what is SaaS, PaaS, IaaC
- what is terraform and its use
- what is bash vs Shell. Simple bash/shell script example
- create Azure account and build AKS cluster (Kubernetes)
- Make a list if port number. Fir example: SSH uses 22
- What is DR ?
- What are Snapshots for database and virtual machines
