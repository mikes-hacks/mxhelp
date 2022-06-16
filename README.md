# mxhelp
Let "Mike Help" prep for your next pentest.  
This little script will update all of your favorite copypasta with IP and Target addresses.  
Easily add any new cheatsheets.  

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

# Easy Edits
Any changes you make will automatically get 'helped' when you run **mxhelp**.  
Make sure to just use reuse the same IP and Target addresses in the files.  


# Secret Sauce (FYI)
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
