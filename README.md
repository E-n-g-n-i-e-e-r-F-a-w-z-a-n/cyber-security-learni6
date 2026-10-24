# Linux Administration and Cybersecurity Practical Lab
# About This Project 
This repository documents my practical learning in Linux, system administration, and cybersecurity at Babtech.
I practice Linux terminal commands to create directory and files, manage file permission, calculate file hashes, inpect running prcesses, and examine network configuration.
## 1. Creating Directories and Files
### Creating my cybersecurity workspace
```bash 
mkdir -p ~/CYBER_LITE/{Linux,Cryptograpy,Cybersecurity}
ls
ls -l
```
### Creating and viewing files
touch student.txt
nano student.txt
cat student.txt

`mkdir` creates directories.
`touch` create an empty file if it does not exit.
`nano` opens a terminal text editor.
`cat` displays file contents.
`ls` lists files and directories
`ls-l` displays detailed file information.
## 2. File Management
### Copying  file 
```bash
cp student.txt ~/CYBER_LITE/Cybersecurity/
```
### Moving and renaming files
```bash
mv ~/CYBER_LITE/Linux/notes.txt ~/CYBER_LITE/Cybersecurity/ mv ~/CYBER_LITE/Cybersecurity/notes.txt ~/CYBER_LITE/Cybersecurity/security_notes.txt

#Finding and searching files
```bash
find ~/CYBER_LITE -name "important.txt"
grep -n "password" file1.txt file2.txt file3.txt
```
### Working with hidden files
```bash
touch .secret
ls -a
cat .secret
```
### Deleting a temporary file
```bash
touch temporary.txt
rm temporary.txt
```

I learned the importance of checking file path carefully before delecting or moving files, especially when handling evidence during security investigation
## 3. File permissions 
### Viewing file permission
```bash
ls -l private.txt
```
### Restricting file access
```bash
chmod 600 private.txt
ls -l private.txt
```
The permission '600' give the file ower read and write permissions while removing permissions for the group and other users
Expected permission pattern  for a regular file:
  -rw-------
### Making a script executable 
```bash
chmod u+x hello.sh
./hello.sh
```
I learned how Linux permissions control access to files and hoe executable permissions allow a script to run.

## 4. File hashing and Cryptography

I practised generaating file hashes using MD5, SHA-256, SHA512.
### Generating hashes

```bash 
md5sum message.txt
sha256sum message.txt
sha512sum message.txt

### Comparing hashes
```bash
sha256sum student1.txt student2.txt
```

Files with identical coontent should produce matchig SHA-256 hashes. changing the ccontent change the hash.
I also practised changing file content and generating hashes again to observe the effect.
 ### What i learned
- MD5 produces a 128 bit hash.
- SHA-256 Produces a 256 bit hash.
- SHA-512 Produces a 512 bit hash.
- Hashing helps check file integrity
- Hashing is not the same as encryption
- MD5 is not suitable for modern security-sensitive integrity application or password storage.

## 5. Process Monitoring 
### Listing running processes
``` bash
ps aux
```

This displays running processes, thier owers, process IDs, CPU and memory usage, and command information.
### Monitoring processes interactively
```bash
top
```
 The `top` command provides a continuously updating view of running processes and system resource usage. Press `q` to exit.

### Checking system uptime

```bash
uptime
```

This displays how long the system has been running, along with load-average information.

I learned that process monitoring can help an analyst investigate unusual resource usage and identify processes that require further examination.

## 6. Network Inspection

### Inspecting network interfaces and IP addresses
```bash
ip addr
```

Displays network interfaces and their assigned IP addresses.

### Checking routes and the default gateway

```bash
ip route
ip route | grep default
```

`ip route` displays the routing table. Filtering for `default` helps identify the default route used to reach destinations outside directly connected networks.

### Using the alternative interface command

tae```bash
ifconfig
```

Displays network interface information when the utility is installed.

### Tracing a network route

```bash
sudo traceroute google.com
```

Shows the route and responding network hops toward the destination when supported by the network.

### Testing connectivity

```bash
ping google.com
```

Tests whether a destination responds to network echo requests and reports round-trip timing when replies are received.

In an earlier virtual-machine lab, I observed the IP address `10.0.2.15` on `eth0` and the default gateway `10.0.2.2`. These values may change depending on the virtual-machine network configuration.

## 7. Linux System Information

```bash
whoami
hostname
pwd
cat /etc/os-release
uname -r
```

These commands identify the current user, computer name, working directory, Linux distribution, and kernel version.

## Skills Practised

- Linux command-line fundamentals
- Directory and file management
- File permissions and ownership inspection
- MD5, SHA-256, and SHA-512 hashing
- Running-process inspection with `ps aux` and `top`
- Network interface and routing inspection
- Basic system information gathering
- Cybersecurity investigation fundamentals

## Learning Status

Beginner cybersecurity learner building practical experience with Linux administration, networking, cryptography, and system investigation.

