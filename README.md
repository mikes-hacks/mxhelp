# mxhelp
Let **Mike Help** you prep for that next pentest.  
This toolkit will update all of your favorite copypasta with IP and Target addresses.  
Flexible and easy to add any new cheatsheets.  

# Usage
```
mxhelp hostip targetip
mxhelp 192.168.119.101 10.1.1.5
```

# Installation
```
cd ~
git clone https://github.com/mikes-hacks/mxhelp.git
chmod +x ~/mxhelp
```

# Alias
To add aliases, first check to see where you normally keep them  
grep alias ~/.bash_aliases ~/.bashrc ~/.zshrc ~/.*

```
(
cat <<EOF
alias mxhelp='~/mxhelp/mxhelp'
alias myip='cat ~/mxhelp/ipoldme'
alias tgt='cat ~/mxhelp/ipoldtgt'
EOF
) >> ~/.bash_aliases
```

# Quick Edits
Changes - Any changes you make will automatically get 'helped' when you run **mxhelp**.  
Additions - Adding a new script is easy, just put it in the ~/mxhelp folder, and add another alias.  
Remember - For any changes you make, just be sure the IP and TGT match with the existing.  

# Secret Sauce (FYI)
The real power comes from the Linux 'sed' command.  
It will update all of the IP's you and your target.  
Several if-else statements at in-code to ensure that you dont wreak your cheatsheets.  
```
find ~/mxhelp/mx* -type f -exec sed -i 's/'"$ipold"'/'"$IP"'/gI' {} \;
find ~/mxhelp/mx* -type f -exec sed -i 's/'"$tgtold"'/'"$TGT"'/gI' {} \;
```

# Batch add your own scripts
1. Rename your scripts to prefix 'mx'
1. Move them to the mxhelp directory
1. Update your Aliases

```
cd ~/pentest/copypasta/
find * -maxdepth 0 -exec mv {} mx{} \;
mv mx* ~/mxhelp/

(
cat <<EOF
alias mxnetcat='cat ~/mxhelp/mxnetcat'
alias myother='cat ~/mxhelp/mxother'
EOF
) >> ~/bash_aliases
```
