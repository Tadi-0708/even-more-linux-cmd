# even-more-linux-cmd
# Master Linux Commands & Utilities Cheat Sheet

## 1. File Searching & Location 
* **locate**: Quickest way to search files by name using a pre-built system database.
  * `locate file.txt` - Search for a file named "file.txt" across the system.
  * `sudo updatedb` - Manually update the search database (do this if newly created files aren't showing up).
* **find**: Real-time recursive search with powerful filtering (by size, date, permissions).
  * `find . -name "config.yaml"` - Find a file by exact name in the current directory.
  * `find /var/log -iname "*.log"` - Case-insensitive search for files ending in .log.
* **grep**: Search text patterns inside file contents.
  * `grep "error" app.log` - Find lines containing the word "error".
* **which**: Locate the binary executable path of a command.
  * `which python3` - Shows where the python3 executable is located.

## 2. Advanced Text Processing & Stream Editing
* **awk**: A powerful pattern scanning and processing language for structured data/columns.
  * `awk '{print $1}' data.txt` - Prints only the first column of text from a file.
  * `awk -F',' '{print $2}' users.csv` - Prints the second column of a CSV file using a comma delimiter.
* **sed**: Stream editor used to filter and transform text dynamically.
  * `sed 's/old-word/new-word/g' configuration.conf` - Substitutes "old-word" with "new-word" across the file without opening it.
  * `sed -i 's/debug=true/debug=false/g' app.env` - Makes changes and updates the file directly in-place (`-i`).
* **cut**: Remove sections from each line of files.
  * `cut -d':' -f1 /etc/passwd` - Cuts out usernames by slicing the system password file using the `:` separator.

## 3. Network Configuration & Diagnostics
* **ping**: Check basic network connectivity to a remote host.
  * `ping google.com`
* **ip a**: Display network interfaces, configurations, and internal IP addresses.
* **netstat / ss**: Investigate active socket connections and listening ports on the host machine.
  * `ss -tuln` - Lists all active TCP/UDP ports currently listening for traffic.
* **traceroute**: Trace the hop-by-hop physical path packets take to a network destination.
  * `traceroute 8.8.8.8` - Maps out network route points to Google DNS.
* **nslookup / dig**: Query Domain Name System (DNS) details for a specific domain name.
  * `dig example.com` - Returns authoritative DNS records for a site.
* **wget / curl**: Fetch or download data and files directly from internet endpoints.

## 4. File & Directory Operations
* **pwd**: Print working directory (shows your current location path).
* **ls**: List directory contents.
  * `ls -la` - List all files, including hidden ones, with detailed permissions/sizes.
* **cd**: Change directory.
  * `cd ..` - Move up one directory level.
* **touch**: Create an empty file or update timestamps.
* **mkdir**: Create a new directory. (`mkdir -p path/to/dir` creates parent folders automatically).
* **cp**: Copy files or directories. (`cp -r` to copy recursively).
* **mv**: Move or rename files and directories.
* **rm**: Delete files or directories. (`rm -rf` deletes recursively and forcefully—use with caution).

## 5. System Information & Monitoring
* **uname**: Get basic operating system info. (`uname -a` displays all kernel details).
* **hostnamectl**: View or modify the system hostname.
* **top / htop**: Interactive real-time process monitoring and system resource usage.
* **ps**: Display a snapshot of currently running active processes.
  * `ps aux` - See all running processes on the system.
* **df -h**: Display disk space usage in human-readable format.
* **du -sh**: Display total disk space used by a specific directory.
* **free -m**: Display free and used memory (RAM) in megabytes.

## 6. User Management & Permissions
* **sudo**: Execute a command with administrative/root privileges.
* **whoami**: Display the active username.
* **passwd**: Create or update passwords for a user.
* **chmod**: Change file file permissions. (`chmod +x script.sh` makes a script executable).
* **chown**: Change file ownership to a different user or group.
