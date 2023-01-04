# mxhelp
With **Mike's Help** you will be ready for your next pentest.  
This toolkit will update all of your favorite copypasta with IP and Target addresses.  
Flexible and easy to add any new cheatsheets.  

# Usage
```
mxhelp hostip targetip
mxhelp 192.168.119.101 10.1.1.5
```

![mxhelp](https://user-images.githubusercontent.com/59158016/176043471-d9c07ce2-19cf-4948-97b5-87a3df1cfde8.gif)

# Installation
```bash
cd ~
git clone https://github.com/mikes-hacks/mxhelp.git
chmod +x ~/mxhelp/mxhelp
```

# Glow
Makes markdown pretty
```bash
wget https://github.com/charmbracelet/glow/releases/download/v1.4.1/glow_1.4.1_linux_amd64.deb -P ~/Downloads
chmod 754 ~/Downloads/glow_1.4.1_linux_amd64.deb
sudo apt install ~/Downloads/glow_1.4.1_linux_amd64.deb
```

# Alias
To add aliases, first check to see where you normally keep them  
grep alias ~/.bash_aliases ~/.bashrc ~/.zshrc ~/.*

```bash
(
cat <<EOF
alias mxhelp='~/mxhelp/mxhelp'
alias mxad='glow ~/mxhelp/mxad'
alias mxbadchars='cat ~/mxhelp/mxbadchars'
alias mxbrutes='glow ~/mxhelp/mxbrutes'
alias mxcurls='glow ~/mxhelp/mxcurls'
alias mxdns='glow ~/mxhelp/mxdns'
alias mxjuicy='glow ~/mxhelp/mxjuicy'
alias mxlinenum='glow ~/mxhelp/mxlinenum'
alias mxnmap='glow ~/mxhelp/mxnmap'
alias mxpersist='glow ~/mxhelp/mxpersist'
alias mxpivot='glow ~/mxhelp/mxpivot'
alias mxreverse='glow ~/mxhelp/mxreverse'
alias mxrootbash='glow ~/mxhelp/mxrootbash'
alias mxsam='glow ~/mxhelp/mxsam'
alias mxsamba='glow ~/mxhelp/mxsamba'
alias mxtest='glow ~/mxhelp/mxtest'
alias mxtransfer='glow ~/mxhelp/mxtransfer'
alias mxpytty='glow ~/mxhelp/mxpytty'
alias mxsqli='glow ~/mxhelp/mxsqli'
alias mxweb='glow ~/mxhelp/mxweb'
alias mxwinenum='glow ~/mxhelp/mxwinenum'
alias myip='cat ~/mxhelp/z_myip'
alias tgt='cat ~/mxhelp/z_tgt'
export common="/usr/share/dirb/wordlists/common.txt"
export commontenk="/usr/share/seclists/Passwords/Common-Credentials/10k-most-common.txt"
export subtopmill="/usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt"
export medium="/usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt"
export rockyou="/usr/share/seclists/Passwords/Leaked-Databases/rockyou.txt"
export mediumdirs="/usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt"
export mediumfiles="/usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt"
export smallpw="/usr/share/seclists/Discovery/Web-Content/raft-small-words.txt"
export ftpdefaults="/usr/share/seclists/Passwords/Default-Credentials/ftp-betterdefaultpasslist.txt"
export besttenfifty="/usr/share/seclists/Passwords/Common-Credentials/best1050.txt"
EOF
) >> ~/.bash_aliases
```
# Refresh
Start a new Terminal after you install.  
This will reload your aliases.  


# Quick Edits
Changes - Any changes you make will automatically get 'helped' when you run **mxhelp**.  
Additions - Adding a new script is easy, just put it in the ~/mxhelp folder, and add another alias.  
Remember - For any changes you make, just be sure the IP and TGT match with the existing.  

# Secret Sauce (FYI)
The real power comes from the Linux 'sed' command.  
It will update all of your IP's for Host and Target.  
The script will also run checks to make sure you dont wreak your cheatsheets.  
```bash
find ~/mxhelp/mx* -type f -exec sed -i 's/'"$ipold"'/'"$IP"'/gI' {} \;
find ~/mxhelp/mx* -type f -exec sed -i 's/'"$tgtold"'/'"$TGT"'/gI' {} \;
```

# Batch add your own scripts
1. Rename your scripts to prefix 'mx'
1. Move them to the mxhelp directory
1. Update your Aliases

```bash
cd ~/pentest/copypasta/
find * -maxdepth 0 -exec mv {} mx{} \;
mv mx* ~/mxhelp/

(
cat <<EOF
alias mxnetcat='cat ~/mxhelp/mxnetcat'
alias mxother='cat ~/mxhelp/mxother'
EOF
) >> ~/bash_aliases
```
