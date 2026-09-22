# Hack The Box — Telnet Lab

## Objective

Identify the services available on the target, connect to the **Telnet** service, and locate the flag in the `root` user's home directory.

## 1. VPN Connection

The connection to the Hack The Box network was established using **OpenVPN**.

## 2. Connectivity Test

The `ping` command was used to verify connectivity to the target:

```bash
ping <TARGET_IP>

ping uses ICMP Echo Requests to check whether the host is reachable.

## 3. Port Enumeration

Nmap was used to identify open ports:

nmap <TARGET_IP>

During the enumeration, the following port was identified:

23/tcp

Port 23/TCP is associated with the Telnet service.

## 4. Telnet Connection

A connection was established to the service:

telnet <TARGET_IP> 23

Access was obtained using the username identified in the exercise and a blank password.

After logging in, the current user was confirmed with:

whoami

Result:

root
5. Locating the Flag

After gaining access as root, the user's home directory was accessed:

cd
pwd
ls -la

The file containing the flag was identified, and its contents were displayed using:

cat <FILE_NAME>

The flag is not included in this write-up.

## Tools Used
OpenVPN — VPN connection to the lab environment
Nmap — Port enumeration
Ping — Connectivity testing
Telnet — Remote access
Linux CLI — System navigation and interaction

## Concepts Learned
Connecting to laboratory environments through a VPN
ICMP and connectivity testing
Basic port enumeration
Identifying services based on port numbers
Using Telnet
Navigating the Linux filesystem
Reading files from the command line

## Process Summary
OpenVPN
   ↓
Ping
   ↓
Nmap
   ↓
23/tcp — Telnet
   ↓
Telnet
   ↓
Login as root
   ↓
Locate the flag

Lab completed successfully.
