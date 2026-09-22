# FTP Lab

## Description
-> In this lab, I learned how to identify and interact with an FTP service running on a target machine.
## Enumeration

First, I used Nmap to identify open ports and services:

```bash
nmap -sV -p 21 10.129.221.182
````

The scan showed:

```
21/tcp open  ftp  vsftpd 3.0.3
```

The FTP service is running **vsftpd 3.0.3**.
## FTP

FTP stands for **File Transfer Protocol**.

The FTP service usually listens on **port 21**.

FTP sends data without encryption. A secure alternative that uses SSH is SFTP (SSH File Transfer Protocol).
## Connecting to the FTP Server

I connected to the target using the FTP client:

```
ftp 10.129.221.182
```

The FTP server allowed an anonymous login:

```
Name: anonymous
Password:
```

The server responded:

```
230 Login successful.
```

The FTP response code **230** indicates that the login was successful.

## Listing Files

After logging in, I used `ls` to list the files available on the server:

```
ls
```

The server contained:

```
-rw-r--r--    1 0 0 32 Jun 04 2021 flag.txt
```

## Downloading the Flag

I downloaded the file using the FTP `get` command:

```
get flag.txt
```

Then I exited the FTP client:

```
bye
```

Finally, I displayed the contents of the downloaded file:

```
cat flag.txt
```

The output contained the flag required by the HTB lab.

## Commands Learned

|Command|Purpose|
|---|---|
|`ping`|Test connectivity using ICMP|
|`nmap -sV`|Detect service versions|
|`ftp`|Connect to an FTP server|
|`ls`|List files and directories|
|`get`|Download a file|
|`bye`|Exit the FTP client|
|`cat`|Display file contents|
## Conclusion

This lab demonstrated how to:

- Identify an FTP service with Nmap.
- Determine the FTP service version.
- Connect to an FTP server.
- Log in using the `anonymous` account.
- List files on the server.
- Download a file using `get`.
- Read the downloaded flag.
