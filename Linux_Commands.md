# Ubuntu Command Guide

This guide covers the 40 most used commands on Ubuntu, categorized into different sections for easier navigation.

## Table of Contents
1. [System Information](#system-information)
2. [File Management](#file-management)
3. [Directory Navigation](#directory-navigation)
4. [File Viewing and Editing](#file-viewing-and-editing)
5. [Package Management](#package-management)
6. [User Management](#user-management)
7. [Network Management](#network-management)
8. [Process Management](#process-management)
9. [Disk Management](#disk-management)
10. [Permission Management](#permission-management)
11. [Compression and Archiving](#compression-and-archiving)

---

## System Information

### 1. `uname`
Displays system information.

```bash
uname -a
```

### 2. `hostname`
Shows or sets the system's hostname.

```bash
hostname
```

### 3. `uptime`
Shows how long the system has been running.

```bash
uptime
```

### 4. `top`
Displays system tasks and resource usage.

```bash
top
```

### 5. `htop`
An improved version of `top`.

```bash
htop
```

### 6. `free`
Displays memory usage.

```bash
free -h
```

---

## File Management

### 7. `ls`
Lists directory contents.

```bash
ls -l
```

### 8. `cp`
Copies files and directories.

```bash
cp source.txt destination.txt
```

### 9. `mv`
Moves or renames files and directories.

```bash
mv oldname.txt newname.txt
```

### 10. `rm`
Removes files or directories.

```bash
rm filename.txt
rm -r directory/
```

### 11. `touch`
Creates an empty file or updates the timestamp.

```bash
touch newfile.txt
```

---

## Directory Navigation

### 12. `cd`
Changes the current directory.

```bash
cd /path/to/directory
```

### 13. `pwd`
Prints the current working directory.

```bash
pwd
```

### 14. `mkdir`
Creates a new directory.

```bash
mkdir new_directory
```

### 15. `rmdir`
Removes an empty directory.

```bash
rmdir empty_directory
```

---

## File Viewing and Editing

### 16. `cat`
Concatenates and displays file content.

```bash
cat file.txt
```

### 17. `less`
Views file content one page at a time.

```bash
less file.txt
```

### 18. `more`
Views file content, similar to `less`.

```bash
more file.txt
```

### 19. `nano`
A simple text editor.

```bash
nano file.txt
```

### 20. `vim`
A powerful text editor.

```bash
vim file.txt
```

---

## Package Management

### 21. `apt-get`
Installs, updates, and removes packages.

```bash
sudo apt-get update
sudo apt-get install package_name
```

### 22. `apt-cache`
Searches for packages.

```bash
apt-cache search package_name
```

### 23. `dpkg`
Manages individual Debian packages.

```bash
sudo dpkg -i package.deb
sudo dpkg -r package_name
```

---

## User Management

### 24. `adduser`
Adds a new user.

```bash
sudo adduser username
```

### 25. `usermod`
Modifies user information.

```bash
sudo usermod -aG groupname username
```

### 26. `passwd`
Changes user password.

```bash
passwd username
```

### 27. `deluser`
Deletes a user.

```bash
sudo deluser username
```

---

## Network Management

### 28. `ifconfig`
Displays or configures network interfaces.

```bash
ifconfig
```

### 29. `ping`
Tests network connectivity.

```bash
ping google.com
```

### 30. `netstat`
Displays network connections, routing tables, and more.

```bash
netstat -tuln
```

### 31. `wget`
Downloads files from the internet.

```bash
wget http://example.com/file.zip
```

### 32. `curl`
Transfers data from or to a server.

```bash
curl http://example.com
```

---

## Process Management

### 33. `ps`
Displays currently running processes.

```bash
ps aux
```

### 34. `kill`
Terminates a process.

```bash
kill process_id
```

### 35. `pkill`
Terminates processes by name.

```bash
pkill process_name
```

### 36. `jobs`
Lists background jobs.

```bash
jobs
```

### 37. `bg`
Resumes a job in the background.

```bash
bg job_id
```

### 38. `fg`
Brings a background job to the foreground.

```bash
fg job_id
```

---

## Disk Management

### 39. `df`
Displays disk space usage.

```bash
df -h
```

### 40. `du`
Displays file and directory disk usage.

```bash
du -sh /path/to/directory
```

---

## Permission Management

### 41. `chmod`
Changes file permissions.

```bash
chmod 755 filename.txt
```

### 42. `chown`
Changes file owner and group.

```bash
chown user:group filename.txt
```

---

## Compression and Archiving

### 43. `tar`
Archives files.

```bash
tar -cvf archive.tar file1 file2
tar -xvf archive.tar
```

### 44. `gzip`
Compresses files.

```bash
gzip filename.txt
gunzip filename.txt.gz
```

### 45. `zip`
Compresses files into a ZIP archive.

```bash
zip archive.zip file1 file2
unzip archive.zip
```
