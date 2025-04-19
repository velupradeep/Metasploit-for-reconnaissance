```
NAME : PRADEEP V
REG NO : 212223240119
DEPT :AIML
```
# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system


## OUTPUT:
![ID](https://github.com/user-attachments/assets/3fac5b1e-363a-4f4a-bc1f-d225c3ac3c89)



## POSTGRESQL


## OUTPUT:
![02](https://github.com/user-attachments/assets/4a46a1b8-8ebb-4f72-b53b-026fbd1ffe41)


## msfdb :

## OUTPUT:
![03](https://github.com/user-attachments/assets/2efe3c40-c37c-48a3-b708-964c056da52c)

## Invoke msfconsole:

## OUTPUT:

![001](https://github.com/user-attachments/assets/0d82f99d-8ecf-42df-97cd-b13204685f54)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT

![05](https://github.com/user-attachments/assets/a1dd4118-113e-4cfc-995e-4b2d1410929d)

## Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

 ## OUTPUT
 
![06](https://github.com/user-attachments/assets/691e8f68-7208-492e-bb90-0b5bd6788c08)
## STEP 4:
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
## OUTPUT:
![08](https://github.com/user-attachments/assets/238189e5-c59c-4340-bb85-0b2ca9bde6cf)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
## OUTPUT:
![09](https://github.com/user-attachments/assets/00eeff83-e74d-4bc5-a00d-821428186dc2)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
## OUTPUT:
![10](https://github.com/user-attachments/assets/b5d0af80-116b-4bc2-8f37-140645bba5cd)

The info command provides information regarding a module or platform,
## OUTPUT:
![11](https://github.com/user-attachments/assets/db0f321e-add0-47ff-8534-31a7aab57aee)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init
## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
## OUTPUT:
![12](https://github.com/user-attachments/assets/bc84e442-a15a-4881-abcb-f6737a34ee87)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
## OUTPUT:
![13](https://github.com/user-attachments/assets/2d555d67-0e4d-4b24-b78f-4555fd839e77)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
## OUTPUT :
![14](https://github.com/user-attachments/assets/18b86061-b729-4cbc-baa7-edc12779494a)
Use the set rhosts command to set the parameter and run the module, as follows:
## OUTPUT :
![15](https://github.com/user-attachments/assets/c2605810-9243-4aa4-b99a-6c6255182396)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
## OUTPUT :
![16](https://github.com/user-attachments/assets/c122efcd-e7c4-4c27-9e9e-3e40815496d6)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
## OUTPUT :
![18 l](https://github.com/user-attachments/assets/12431d41-f034-4796-9f96-925ce449b8a6)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
