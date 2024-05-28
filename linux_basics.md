## System Monitoring and Resource Management
- `top`: Displays real-time system summary information, including CPU and memory usage.
```bash
top
```

- `htop`: An interactive version of top that provides a more user-friendly interface.
```bash
htop
```
- `free`: Shows memory usage.
```bash
free -h
```
- `vmstat`: Provides a snapshot of system performance.
```bash
vmstat 5
```
- `iostat`: Reports CPU and I/O statistics.
```bash
iostat -xz 1
```
- `mpstat`: Displays CPU usage.
```bash
mpstat -P ALL 1
```
- `sar`: Collects, reports, and saves system activity information.
```bash
sar -u 1 5
```
- `ps`: Displays information about active processes.
```bash
ps aux | grep apache2
```
- `pstree`: Shows running processes in a tree-like format.
```bash
pstree
```
- `pmap`: Reports memory map of a process.
```bash
pmap -x <PID>
```
- `kill` / `killall` / `pkill`: Sends signals to processes to terminate them.
```bash
kill -9 <PID>
killall firefox
pkill -f apache2
```
- `nice` / `renice`: Alters the priority of running processes.
```bash
nice -n 10 <command>
renice 10 -p <PID>
```
- `uptime`: Shows how long the system has been running.
```bash
uptime
```

## User and Session Management
- `who`: Displays who is logged in.
```bash
who
```
- `w`: Shows who is logged in and what they are doing.
```bash
w
```
- `last`: Lists last logins.
```bash
last
```
- `lastb`: Shows failed login attempts.
```bash
sudo lastb
```
- `finger`: Displays information about system users.
```bash
finger <username>
```
- `id`: Displays user identity.
```bash
id
```
- `usermod`: Modifies user account.
```bash
sudo usermod -aG sudo <username>
```
- `passwd`: Changes user password.
```bash
passwd <username>
```
- `useradd` / `adduser`: Adds a new user.
```bash
sudo adduser <username>
```
- `userdel` / `deluser`: Deletes a user.
```bash
sudo userdel <username>
```
- If you prefer to use `userdel`, you can use the `-r` option to remove the home directory as well:
```bash
sudo userdel -r <username>
```
- `groupadd`: Adds a new group.
```bash
sudo groupadd <groupname>
```
- `groupdel`: Deletes a group.
```bash
sudo groupdel <groupname>
```
- `chage`: Changes user password expiry information.
```bash
sudo chage -l <username>
```
- `su`: Switches to another user account.
```bash
su - <username>
```
- `sudo`: Executes a command as another user.
```bash
sudo apt-get update
```

## System and Kernel Information
- `uname -a`: Displays system information.
```bash
uname -a
```
- `hostnamectl`: Sets the hostname or views system information.
```bash
hostnamectl
```
- `dmesg`: Prints kernel ring buffer messages.
```bash
dmesg | tail
```
- `lsmod`: Lists loaded kernel modules.
```bash
lsmod
```
- `modprobe`: Adds or removes modules from the Linux kernel.
```bash
sudo modprobe -r <module_name>
```
- `sysctl`: Configures kernel parameters at runtime.
```bash
sudo sysctl -a
```
- `lshw`: Lists hardware information.
```bash
sudo lshw -short
```
- `lsblk`: Lists information about all available or specified block devices.
```bash
lsblk
```
- `lscpu`: Displays information about the CPU architecture.
```bash
lscpu
```

## Disk and File System Management
- `df`: Reports file system disk space usage.
```bash
df -h
```
- `du`: Estimates file space usage.
```bash
du -sh /var/*
```
- `fdisk`: Manipulates disk partition table.
```bash
sudo fdisk -l
```
- `ls`: Lists directory contents.
```bash
ls -al
```
- `find`: Searches for files in a directory hierarchy.
```bash
find /var/log -name "*.log"
```
- `mount` / `umount`: Mounts or unmounts file systems.
```bash
sudo mount /dev/sda1 /mnt
sudo umount /mnt
```
- `blkid`: Locates/prints block device attributes.
```bash
sudo blkid
```
- `parted`: Manipulates disk partitions.
```bash
sudo parted /dev/sda print
```
- `mkfs`: Builds a Linux file system.
```bash
sudo mkfs.ext4 /dev/sda1
```
- `tune2fs`: Adjusts tunable file system parameters.
```bash
sudo tune2fs -l /dev/sda1
```

## Log Management
- `journalctl`: Views systemd journal logs.
```bash
sudo journalctl -xe
```
- `tail`: Outputs the last part of files.
```bash
tail -f /var/log/syslog
```
- `head`: Outputs the first part of files.
```bash
head -n 20 /var/log/syslog
```
- `less`: Views file contents interactively.
```bash
less /var/log/syslog
```
- `grep`: Searches for patterns in files.
```bash
grep "error" /var/log/syslog
```
- `awk`: Pattern scanning and processing language.
```bash
awk '{print $1}' /var/log/syslog
```
- `sed`: Stream editor for filtering and transforming text.
```bash
sed -n '1,10p' /var/log/syslog
```
- `logger`: Adds entries to the system log.
```bash
logger "This is a test log message"
```

## Network Management
- `ifconfig` / `ip`: Configures network interfaces.
```bash
ifconfig -a
ip addr show
```
- `ping`: Checks connectivity to another host.
```bash
ping google.com
```
- `traceroute`: Traces the route packets take to a network host.
```bash
traceroute google.com
```
- `netstat` / `ss`**: Displays network connections, routing tables, interface statistics.
```bash
netstat -tuln
ss -tuln
```
- `iptables`: Configures IP packet filter rules.
```bash
sudo iptables -L
```
- `tcpdump`: Captures network packets.
```bash
sudo tcpdump -i eth0
```
- `nslookup` / `dig`: Queries DNS servers.
```bash
nslookup google.com
dig google.com
```
- `nmap`: Network exploration tool and security/port scanner.
```bash
nmap -sP 192.168.1.0/24
```

## Package Management
- `apt-get` / `apt`: Handles packages for Debian-based distributions.
```bash
sudo apt-get update
sudo apt-get upgrade
```
- `dpkg`: Package manager for Debian-based distributions.
```bash
dpkg -l
```
- `snap`: Manages snap packages.
```bash
sudo snap install <package>
```
- `yum` / `dnf`: Handles packages for RPM-based distributions.
```bash
sudo yum update
sudo dnf update
```

## Miscellaneous
- `cron` / `crontab`: Schedules periodic background tasks.
```bash
crontab -e
```
- `at`: Schedules one-time tasks.
```bash
echo "touch /tmp/testfile" | at now + 1 minute
```
- `systemctl`: Controls the systemd system and service manager.
```bash
sudo systemctl status apache2
```
- `service`: Runs a System V init script.
```bash
sudo service apache2 status
```
- `timedatectl`: Controls system time and date settings.
```bash
timedatectl
```

## Example Scenarios
- Monitoring CPU and Memory Utilization:

```bash
top
htop
free -h
```
- Killing a High Resource-consuming Process:

```bash
ps aux --sort=-%cpu | head -n 10
kill -9 <PID>
```
- Checking Logged-in Users:

```bash
who
w
last
```
- Forcing Kill Sessions:

```bash
pkill -u <username>
```
- Checking Kernel Version:

```bash
uname -r
```
- Patching Systems:

```bash
sudo apt-get update
sudo apt-get upgrade
```
- Checking Logs for User Commands:

```bash
cat /var/log/auth.log
```
- Checking Server Reboot Reasons:

```bash
last reboot
journalctl -xe | grep reboot
```
