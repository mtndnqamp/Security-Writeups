#OpenCTI, first steps into threat intelligence.

Today I set up an OpenCTI instance. OpenCTI is an open source threat intelligence platform that is highly customizable with a intuitive interface. I wanted to do this as I am interested in the topic of Threat intelligence within cyber security. Deploying my own instance of OpenCTI will let me explore this interest more.
I chose OpenCTI over MISP as it can be hosted easily with docker containers and scaled to my needs.

Deploying the base install of OpenCTI was straightforward; I first downloaded the docker-compose and .env files, modified the password and secrets values, uploaded the modified files into a portainer instance, and deployed it as a stack. There were a few issues with port numbers being taken and login credentials not syncing between client and service, however these where minor issues. 
After deploying OpenCTI, the instance looked like this.

 
An empty threat intel dashboard is no use to anyone! , so the next step was to start deploying connectors to ingest data.
I selected the following connectors
-	Alien vault (An opensource threat exchange platform)
-	AbuseIPDB (A database of malicious or abused ip’s)
-	CISA KEV catalog (The latest known exploit cve’s)
-	Phishunt (A feed of phishing activities)
-	Circl Osint feed (A feed with OSINT findings from circl)
To add these connectors, I just needed add to them into the main docker compose file on portainer, and redeploy the stack.
With the connectors now added, OpenCTI is now filling up 



The next step will be creating custom dashboards from the data, and possibly adding a custom taxii feed in the next few months. 
Overall im happy with my small deployment of OpenCTI, it helped build my knowledge of docker and threat intelligence practices more broadly. 
