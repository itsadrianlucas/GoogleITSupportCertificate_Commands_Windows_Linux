BASIC NAVIGATING COMMANDS

WINDOWS
pwd/Get-Location (shows the current directory, valid in both PowerShell and Linux)
history/Get-History (shows the current directory, valid in both PowerShell and Linux)
ls/dir/GetChild-Item (list items in the directory)
cd (change Directory/Access a directory)
mkdir (create directories)
rm/Remove-Item (remove files in a directory)
mv/Move-Item (moves or renames files)
cp/Copy-Item (copies files and directories)
echo (Creates or displays content of a file)
Start (used to start programs or open files)
cat/Get-Content (displays the contents of files)
more/Out-Host (views files page by page)
Get-Alias (used to list command aliases)
echo/Write-Output (display text or output values)
findstr (finds text in files "for example ctrl + f")

> (output redirection)
>> (appends content to a file)
2> (redirects errors to a file)
< (input redirection, valid in both Linux and PowerShell)
| (chains commands together, common in both)

LINUX:
pwd (shows the current directory)
history (shows the command history)
ls (list items in the directory)
cd (change Directory/Access a directory)
mkdir (creates directories)
rm (remove files in a directory)
mv (moves or renames files)
cp (copies files and directories)
echo (creates or displays content of files or output values)
cat (displays the contents of files)
more (views files page by page)
grep (finds text in files)

USERS AND PERMISSIONS

WINDOWS
Get-LocalUser (checks the Computer Users/Privileges)
Get-LocalGroup (checks the Computer Groups)
Get-LocalGroupMember "Administrators" (checks the Group's members)
net user Adrian * (Set a new password for an user in the computer)
net user Adrian /logonpasswordchg:yes (User will be forced to change the password on next login)
net user Adrian * /add (Add a new user in the computer)
net user Adrian password /add /logonpasswordchg:yes (mixing the 2 commands above to add and force reset password on next login)
net user Adrian /del (delete a user from the computer)
Removal-LocalUser Adrian (delete a user from the computer same as "net")
icacls C:\Users\adria\Desktop\ (Shows the permission the user have on folder/file)
icacls 'C:\Vacation_Pictures' /grant 'Everyone: (OI)(CI)(R)'  (add permission to a group of users)
icacls 'C:\Vacation_Pictures' /remove Everyone: (remove permissions to a group of users in this case "everyone group")

LINUX
cat /etc/group (checks the Computer Groups and members)
cat /etc/passwd (checks the Computer Users/Privileges)
passwd Adrian (Set a new password for an user in the computer)
sudo passwd -e "Adrian" (User will be forced to change the password on next login)
sudo useradd Adrian (Add a new user in the computer)
sudo userdel Adrian (delete a user from the computer)
ls -l ~/my_file (Shows the permission the user have on folder/file)
chmod u+x ~/my_cool_file (add permissions for = "u"User / "g"group / "o"otherusers)
chmod u-x ~/my_cool_file (remove permissions "x or 1"executable / "w or 2"write / "r or 4"read)
chmod 754 /my_cool_file (add permissions using numericals ex = "1+2+4= 7"User / "4+1= 5"group / "4"otherusers)
sudo chown adrian my_cool_file (Changes the owner of a file, in this case the user "adrian")
sudo chgrp best_group_ever my_cool_file (Changes the group of a file)

PACKAGES AND SOFTWARE MANAGEMENT

WINDOWS
Compress-Archive -path C:\Users\Adria\Coolfile ~\Adria\Coolfile.zip (Compress a file using first the path source and then destiny)
Install-Package -Name awesomesoftware -Source chocolatey (installing a package using PowerShell and specifying Chocolatey as the source.)
Get-Package -Name TestPackage (Check if the package exists in the computer)

LINUX
sudo dpkg -i atom-amd64.deb (Install a Debian package "flag I" app Atom)
sudo dpkg -r atom-amd64.deb (remove a Debian package "flag R")
dpkg -l  (Lists my packages installed)
sudo apt install gimp (Install gimp using the package Manager Apt)
sudo apt remove gimp (removes gimp using the package Manager Apt)
sudo apt updated (Update the list of packages in the repository)
sudo apt upgrade (Install the packages updated in the machine)
7z e my_achive.tar (Extracts a file in Linux(Debian) flag e is for extraction)
uname -r (Checks the version of the Kernel is being used in Linux)
sudo apt full-upgrade (Updates the Kernel of the OS)

FILESYSTEM MANAGEMENT

WINDOWS
Diskpart (Tool to manager disks in CLI)
list disk (Lists the disks connected to the computer)
select disk (Selects the disk)
clean (formats the disk and remove all partitions created before)
create partition primary (Creates a partition in the disk)
select partition (selects the partition created)
active (Activates the current partition)
format FS=NTFS label=my-test-drive quick (This command is formatting the drive with NTFS format on quick mode)

LINUX
sudo parted -l (lists the disks connected to the computer)
sudo parted /dev/sdb (selects the disk in this case "/dev/sdb")
mklabel gpt (renames/Set a label to the disk/partition table)
mkpart primary ext4 1mib 5gib (creates a partition in the device setting the partition type, the filesystem and size)
sudo mkfs -t ext4 /dev/sdb1 (formatting the partition using the "-t" filesystem settled)
