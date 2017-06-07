## CM Monitoring lab

* What is ubertask optimization?

Answer: The abillity to run "sufficiently small" jobs sequentially within a single JVM

* Where in CM is the Kerberos Security Realm value displayed?

Answer: Administrstion -> Settings -> Kerberos Security Realm (or default_realm)

* Which CDH service(s) host a property for enabling Kerberos authentication?

Answer: Zookeeper, Yarn and HDFS

* How do you upgrade the CM agents?

Answer:  
	* Hosts -> Rerun upgrade wizard  
	* Manualy by upgrading the packages in the hosts (like with yum)
	

* Give the `tsquery` statement used to chart Hue's CPU utilization?

Answer: select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME
(where $SERVICENAME == hue)

* Name all the roles that make up the Hive service

Answer: Gateway, Hiveserver2, Hive metastore server

* What steps must be completed before integrating Cloudera Manager with Kerberos?

Answer: 

* Have Cloudera Manager and CDH Installed
* If You are Using AES-256 Encryption, Have the JCE Policy File installed
* Ensure you have secured communication between the Cloudera Manager Server and Agents 
* Have a AD user which has admin rights
* Get or Create a Kerberos Principal for the Cloudera Manager Server (of the above user)
* Have the following packages installed:
	* openldap-clients on the Cloudera Manager Server host  
	* krb5-workstation, krb5-libs on ALL hosts


