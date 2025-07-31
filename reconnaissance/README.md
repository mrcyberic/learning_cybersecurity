## what is reconnaissance 
- its all about finding exploits of the target 
- gathering info 
- researching about the target 
	- who lead them
	- what type of servers or technologies they use 
	- where are they located at 
	- what do they release without them knowing that can be used as a vulnerability
	- everything about them
and  this can be done using 
# 1 via studying how the website is organised 
- by viewing the web code source 
	- to see if the code contains some kind of comment init that the programmer used to remind him self 
	- and it may or may not be used as exploit or as vulnerability 
- using HTtrack 
	- this site will make sure that we got all the needed file from the website
	- will enable us to visite all things that make the websites offline
	- we try to find how the website is organised what type off tools it used and the security structure 
	- #drawbacks 
			this web file downloader can not show or open interactive files which are made by javascript 
			to over come this 
				use `httrack "https://example.com" -O "./mirror" --user-agent "Mozilla/5.0" "+*.example.com/*" +*.css +*.js +*.jpg +*.png +*.svg`
			change the target address on `example.com` both place
- using link extractor
	- this site will help to get all the link that are used on the website
# 2
via ping , dns, traceroute 
	ping 
		Set Buffer Size (`-s`)

	- This sets the number of data bytes to send in the ICMP packet (excluding headers).

```bash
ping -s 1000 enter the target url here
```

	- Sends a 1000-byte payload in the ICMP echo request.
    
- The total packet size will be 1000 bytes + 28 bytes (IP + ICMP headers).
    
Prevent Fragmentation(`-M do`)

- This sets the **"Don't Fragment" (DF)** flag in the IP header. Used for Path MTU Discovery.

```bash
ping -s 1472 -M do eneter the target url here
```

- `-M do`: tells ping **not to fragment** the packet.
    
- `-s 1472`: 1472 bytes + 28 bytes header = **1500 bytes**, which is the default MTU of most Ethernet networks.
    
- If the packet must be fragmented and `-M do` is set, the ping will fail.
    

 Allow Fragmentation(`-M want`)

Lets the system decide if fragmentation is needed.

```bash
ping -s 2000 -M want example.com
```

- Sends a large packet, but allows fragmentation.

|Option|Description|Example|
|---|---|---|
|`-s SIZE`|Set payload (buffer) size in bytes|`ping -s 1000 google.com`|
|`-M do`|Don’t fragment (fail if needed)|`ping -s 1472 -M do 8.8.8.8`|
|`-M want`|Allow fragmentation if needed|`ping -s 2000 -M want 8.8.8.8`|

- nslookup 
	- active and passive 
		passive uses different source to come up with what is needed
```
		nslookup + enter the target url here 
```


	active is when we are interacting with the server directly this will help more than the passive method

```
		nslookup
		enter the target url here 

	set type=a 
	enter the target url here 

	set type = mx
	enter the target url here

	set type = cname
	enter the target url here
```
		
- traceroute 
	- this command is important to get the ip addresses of all routers that are between this computer and and the serever of the url that we provided 
```
	- traceroute + enter the target url here
```
# 3
via websites 
- like netcraft and wayback
	- netcraft =give the url and it will provide a detailed info about the servers 
	- wayback 
		- this site will provide a secreenshots of every possible timeline of the websiite that we have been looking on 
		- starts form the begining up to now 
		- basically shows the history of a targeted website 
via whois 
	both on command and on website 
		`whois + enter the target here`
via people search
	to find out more about the person
via social medias and email
# 4
via google 
	designed to give what is asked 
	with 32 words limit 
	**use advanced search for mere convenient result**
- operators 
	- single vs combining words
	- using ""
	- boolean = to use and
	- special character  like - to exclude something specific
- advanced operators 
	- rules 
		- no space between the operator and the search term
			- intitle:batman (intitle = operator batman=search term)
		- if space exist use ""
			- intitle:"batman"
		-  can combine operator 
		
	- use **cache:** = to see cached version of google 
	- use **link:** =show a list of web pages that have links to your target 
	- use **related:** = similar web pages  
	- use **info:** =view information google has on the target 
	- use **site:** = look the result on 
	- use **allintitle:**=limits results to those websites with all the search word in the title ' needed words looking on titles'
	- use **intitle:** limit results to documents that contain the search words in the title "search the needed word in the document"
	- use **allinurl:**=limit result to only those web pages with all search words in the url "search the needed word only on urls"
	-  use **inurl:** = limit result to documents that contain the search word in the url
	# google hacking database
	- goolink scanner 
		- gives only completly open for google
	- google honeypot 
		- gives fake results 
	- searchdiggity 
		- web GUI interface that can be added to ggogle
	- gooscan
		- to automate your search 
		-  against google 
	- meragoofil
		- capture files form the target and extract meta data form them 
	- sitegigger 
		- to see if there is a error file on the target 
		- like mis match cache , mis configuration 
# counter measures
1. configure your routers (not to responds to certain traffics)
	1. change your configure your router as another router vendor so the attacker will throw different attack type and that wouldn't work
	2. this is basically giving info for the internet that would work or not giving info that could make vulnerable 
2. use IDS 
	1. detactinc intrusions
3. reconfigure web server
	1. never use default settings
4. enforce security policies 
	1. both physical and theoretical 
	2. not to give up infos unless required on certain rule or form
# things that should be seen
1. what kind of info is being leaked out 
2. avoid soical engineering 
3. the recon work flow 
	1. get pesmissind
	2. determine scope 
	3. recon via whois
	4. recon via dns (nslookup , traceroute, whois)
	5. recon network rages 
	6. recon via search engines using google and document what is resulted form it
	7. recon via websites that re provided for a certain searches (wayback, gdb, netcraft )
	8. recon via email
	9. recon via competitive intelligence hire from competitive companies that are practically enemies 
	10. recon via google hacking 
	11. recon via social engineering
	12. recon via social networks 
	13. compile findings 
# notes 
where can we find the advanced searching quires
- google database and exploit db
- github ( google docking script)
- google advance search
- open source frame work (OSINT Frame work)
where to find sub-domains
- netcraft : to get dns basically --> on web
- subfinder :--> on terminal 
- theharverster :--> on terminal
- sherlock--> on terminal
## deep and dark web foot printing 
search engnes
	torch
## to see the operating system
- shodan  (works for server ) --> web search 
