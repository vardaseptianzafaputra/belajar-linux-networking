# Learning Linux & Networking

This repository contains self-study notes on Linux and basic computer networking as a foundation for learning cybersecurity.

## 🎯 Learning Goals

- Understand how to use the Linux terminal.
- Understand file, folder, and permission management.
- Understand IP addressing, subnetting, gateways, and routing.
- Understand DNS, HTTP/HTTPS, and network connectivity testing.
- Build a foundation for learning Python, SQL, and cybersecurity.

---

## 📚 Stage 1 — Linux Basics & Networking

### 1.1 Terminal and Navigation

| Command | Function |
|---|---|
| `pwd` | Show the current directory |
| `ls` | List directory contents |
| `ls -a` | List contents including hidden files |
| `cd` | Change directory |
| `mkdir` | Create a folder |
| `touch` | Create an empty file |
| `cat` | Display file contents |
| `less` | Read a file with navigation |
| `head` | Show the beginning of a file |
| `tail` | Show the end of a file |
| `nano` | Open a terminal text editor |
| `find` | Search for files or folders |
| `cp` | Copy a file or folder |
| `mv` | Move or rename a file/folder |
| `rm` | Delete a file |
| `rmdir` | Delete an empty folder |

### 1.2 Files, Folders, and Paths

- `.` refers to the current directory.
- `..` refers to the parent directory.
- Names starting with a dot, like `.config`, are usually hidden files/folders.
- `mv catatan.txt catatan-baru.txt` renames a file.
- `mv catatan.txt Dokumen/` moves a file into the `Dokumen` folder.
- A trailing `/` on the destination can clarify that it's a folder, though it's not always required.

### 1.3 Linux Permissions

Basic permissions:

- `r` = read
- `w` = write (modify)
- `x` = execute (run a file or access a directory)
- `u` = user/owner
- `g` = group
- `o` = others

Numeric values:

- `r = 4`
- `w = 2`
- `x = 1`

Examples:

- `chmod 644 catatan.txt` gives the owner read/write, and group/others read-only.
- `chmod 755 skrip.sh` gives the owner read/write/execute, and group/others read/execute.
- `chmod` changes permissions.
- `chown` changes file ownership.
- `sudo` runs a command with administrative privileges if permitted.

> Avoid using `chmod 777` without a clear reason, since it grants full access to everyone.

### 1.4 IP Address and Interface

Ubuntu IP in the virtual machine during practice:

`192.168.64.4/24`

Network interface:

`enp0s1`

Command to check the IPv4 address:

```bash
ip -4 addr show enp0s1
```

The VM's IP can differ from the Mac's IP because it uses UTM's virtual network.

### 1.5 Subnet and CIDR

`/24` means 24 bits are used for the network prefix.

Example `192.168.64.4/24`:

- Host IP: `192.168.64.4`
- Prefix: `/24`
- Subnet mask: `255.255.255.0`
- Network address: `192.168.64.0`
- Broadcast address: `192.168.64.255`
- Host bits: 8

The usable host range on this subnet is generally `192.168.64.1` to `192.168.64.254`, depending on network configuration.

### 1.6 Gateway and Routing

Gateway during practice:

`192.168.64.1`

Command to check routing:

```bash
ip route
```

The gateway is usually the exit path to other networks when no more specific route exists.

### 1.7 DNS

DNS translates domain names into IP addresses.

Commands practiced:

```bash
getent hosts google.com
nslookup google.com
```

If access by IP address works but domain name resolution fails, DNS is one of the things to check.

### 1.8 Connectivity Testing

Commands practiced:

```bash
ping -c 4 192.168.64.1
ping -c 4 8.8.8.8
ping -c 4 google.com
```

- `-c 4` limits the number of packets sent to four.
- `0% packet loss` means all sent packets received a reply.
- `100% packet loss` means no packets received a reply. This doesn't always prove the whole internet connection is down, since the target or network may be blocking pings.

### 1.9 HTTP and HTTPS

Commands practiced:

```bash
curl -I https://www.google.com/
curl -IL https://google.com
```

- `curl` sends a request to a URL.
- `-I` requests only the response headers.
- `-L` follows redirects.
- HTTP `301` indicates a permanent redirect.
- HTTP `200` indicates a successful request.

---

## 📝 Stage 1 Evaluation

Main evaluation result: **10/12 (83.3%)**.

Areas that need reinforcement:

1. Understanding the meaning of `100% packet loss`.
2. Distinguishing a host IP from a network address.

Additional practice also covered `chmod`, `sudo`, `chown`, `find`, `cat`, `mv`, and `ls -a`.

## 🚧 Next Topics

Upcoming material to study and practice gradually:

- Strengthening subnetting and network address calculation.
- Further routing concepts.
- Network checking and troubleshooting.
- A final hands-on evaluation.

Note: `traceroute` has not yet been practiced in this learning session.

---

## 📌 Learning Principles

- Hands-on practice in Ubuntu via UTM.
- Understand a command's function before using it.
- Avoid running risky commands without understanding their impact.
- Update notes only after material has actually been learned.
