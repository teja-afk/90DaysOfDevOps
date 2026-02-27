📁 File System Commands
Command	Usage
pwd	Print current working directory
ls -la	List all files (including hidden) with details
cd <dir>	Change directory
mkdir <dir>	Create new directory
rm -rf <dir>	Remove directory recursively
cp -r src dest	Copy directory recursively
mv src dest	Move or rename file
touch file.txt	Create empty file
find / -name file.txt	Search file by name
du -sh *	Show disk usage of files/folders
df -h	Show disk space usage
tree	Display directory structure

⚙️ Process Management Commands
Command	Usage
ps aux	List all running processes
top	Real-time process monitoring
htop	Enhanced process viewer (if installed)
kill <PID>	Terminate process by PID
kill -9 <PID>	Force kill process
pkill <name>	Kill process by name
systemctl status <service>	Check service status
systemctl start <service>	Start a service
systemctl stop <service>	Stop a service
journalctl -xe	View system logs
journalctl -u nginx	View logs for specific service

🌐 Networking & Troubleshooting Commands
Command	Usage
ip addr	Show IP addresses
ping google.com	Check connectivity
curl http://localhost	Test HTTP endpoint
netstat -tulnp	Show listening ports
ss -tulnp	Modern alternative to netstat
dig google.com	DNS lookup
traceroute google.com	Trace network path
hostname -I	Show system IP address

📜 Log & File Inspection Commands
Command	Usage
cat file.txt	Display file content
less file.txt	View large file with scrolling
head -n 20 file.txt	Show first 20 lines
tail -n 20 file.txt	Show last 20 lines
tail -f app.log	Follow live logs
grep "error" file.txt	Search text in file
chmod 755 file.sh	Change file permissions
chown user:group file	Change ownership

🔐 User & Permission Management
Command	Usage
whoami	Show current user
id	Show user UID/GID
useradd username	Create new user
passwd username	Set user password
groupadd groupname	Create group
usermod -aG group user	Add user to group
sudo <command>	Execute command as root
