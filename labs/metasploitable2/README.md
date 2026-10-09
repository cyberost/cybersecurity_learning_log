# Metasploitable 2: Network Enumeration & Metasploit Testing

## Objective

Practice network enumeration, identify exposed services, and understand how to select and troubleshoot exploits in an authorized lab.

## Lab Environment

* **Attacker:** Kali Linux
* **Target:** Metasploitable 2
* **Virtualization:** Oracle VirtualBox
* **Tools:** Nmap, Metasploit Framework

## 1. Network Discovery

Confirmed connectivity between Kali Linux and the intentionally vulnerable target.

* Kali Linux IP: `192.168.1.3`
* Metasploitable 2 IP: `192.168.1.4`
* Connectivity test: `ping`
* Result: Successful connectivity with 0% packet loss.

## 2. Nmap Enumeration

Command used:

```bash
nmap -p 445 -sV 192.168.1.4
```

**Finding:** Port 445 was open, and service detection identified a Samba/Unix environment.

**Security relevance:** Exposed SMB services can increase risk when vulnerable versions or insecure configurations are present.

## 3. Metasploit Testing

### Test A: MS08-067

**Module:** `exploit/windows/smb/ms08_067_netapi`

**Result:** Unsuccessful. Metasploit identified the target as Unix and reported that no matching target was available.

**Analysis:** MS08-067 targets vulnerable Windows systems. The identified Unix/Samba environment did not match the expected target.

### Test B: Samba usermap_script

**Module:** `exploit/multi/samba/usermap_script`

**Result:** No session was established during the test.

**Analysis:** A successful exploit was not confirmed. Further validation of the Samba version, configuration, and vulnerability status would be required.

## 4. Key Findings

* Network connectivity and service enumeration worked.
* Port 445 exposed an SMB/Samba service.
* The Windows-specific exploit did not match the identified target.
* The Samba exploit test did not establish a session.
* No successful exploitation was demonstrated.

## 5. Remediation Recommendations

* Keep Samba and other network services updated.
* Disable unnecessary SMB services.
* Restrict SMB access to trusted hosts and network segments.
* Review service configurations and permissions.
* Monitor for unusual SMB connections and exploit attempts.

## 6. Lessons Learned

This lab reinforced the importance of validating the operating system, service, version, and vulnerability before selecting an exploit. A failed exploit attempt is not proof that a system is secure; it means the tested approach did not demonstrate successful exploitation.

## Evidence

Screenshots of connectivity tests, Nmap output, and Metasploit results will be stored in the `screenshots/` directory.

## Ethical Use

All testing was conducted in an isolated educational lab against an intentionally vulnerable virtual machine. No public or third-party systems were targeted.
