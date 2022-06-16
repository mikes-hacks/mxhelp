# mxhelp
Help for your pentest scripts

# Installation
```
git clone https://github.com/mikes-hacks/mxhelp.git
mv mxhelp/ ~/.cheatsheets/
chmod +x ~/.cheatsheets/mxhelp

(
cat <<EOF
alias mxhelp='~/.cheatsheets/mxhelp'
alias myip='cat ~/.cheatsheets/ipoldme'
alias tgt='cat ~/.cheatsheets/ipoldtgt'
EOF
) >> ~/.bash_aliases
#) >> ~/.bashrc  ..optional
#) >> ~/.zshrc   ..optional
```

# Usage
```
mxhelp hostip targetip
mxhelp 192.168.119.101 10.1.1.5
```

# Secret Sauce (FYI)
```
find ~/.cheatsheets/mx* -type f -exec sed -i 's/'"$ipold"'/'"$IP"'/gI' {} \;
find ~/.cheatsheets/mx* -type f -exec sed -i 's/'"$tgtold"'/'"$TGT"'/gI' {} \;
```
