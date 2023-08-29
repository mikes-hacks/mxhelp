# mxhelp
With **Mike's Help** you will be ready for your next pentest.  
This toolkit will update all of your favorite copypasta with IP and Target addresses.  
Flexible and easy to add any new cheatsheets.  

# Usage
```
mxhelp hostip targetip
mxhelp 192.168.119.101 10.1.1.5
```

![mxhelp](https://user-images.githubusercontent.com/59158016/210803472-881936a9-e464-40ec-930e-ea6eeeb330f0.gif)

# Installation
```bash
cd ~
git clone https://github.com/mikes-hacks/mxhelp.git
chmod +x ~/mxhelp/mxhelp
```

# Add Colors
```
cd ~/Downloads
wget https://github.com/owenthereal/ccat/releases/download/v1.1.0/linux-amd64-1.1.0.tar.gz
tar xvf linux-amd64-1.1.0.tar.gz 
sudo cp linux-amd64-1.1.0/ccat /usr/bin/ccat
sudo chmod 755 /usr/bin/ccat
```

# Alias
To add aliases, first check to see where you normally keep them  
grep alias ~/.bash_aliases ~/.bashrc ~/.zshrc ~/.*

```bash
(
cat <<EOF
#mxhelp
alias mxhelp='~/mxhelp/mxhelp'
alias mxad='ccat ~/mxhelp/mxad'
alias mxbadchars='ccat ~/mxhelp/mxbadchars'
alias mxbrutes='ccat ~/mxhelp/mxbrutes'
alias mxcurls='ccat ~/mxhelp/mxcurls'
alias mxdns='ccat ~/mxhelp/mxdns'
alias mxjuicy='ccat ~/mxhelp/mxjuicy'
alias mxlinenum='ccat ~/mxhelp/mxlinenum'
alias mxnmap='ccat ~/mxhelp/mxnmap'
alias mxpersist='ccat ~/mxhelp/mxpersist'
alias mxpivot='ccat ~/mxhelp/mxpivot'
alias mxreverse='ccat ~/mxhelp/mxreverse'
alias mxrootbash='ccat ~/mxhelp/mxrootbash'
alias mxsam='ccat ~/mxhelp/mxsam'
alias mxsamba='ccat ~/mxhelp/mxsamba'
alias mxtest='ccat ~/mxhelp/mxtest'
alias mxtransfer='ccat ~/mxhelp/mxtransfer'
alias mxpytty='ccat ~/mxhelp/mxpytty'
alias mxsqli='ccat ~/mxhelp/mxsqli'
alias mxweb='ccat ~/mxhelp/mxweb'
alias mxwinenum='ccat ~/mxhelp/mxwinenum'
alias myip='ccat ~/mxhelp/z_myip'
alias tgt='ccat ~/mxhelp/z_tgt'
alias ccat='ccat --bg="dark" -G Decimal="*green*" -G Keyword="blue" -G Punctuation="*yellow*" -G Plaintext="reset" -G String="brown" -G Type="*white*" -G Literal="fuchsia"'
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

# FAQ
1. Why isn't this in Markdown?
`A favorite feature is double-click-and-paste-to-terminal. This makes it easy to use the scripts. Adding markdown tags and colors caused the content to have extra spacing which is harder to quick-copy. Leaving it as plain-text allows the mouse to quick-click and use the commands.`

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
