# dev-env
A place to keep my dev environment preferences and setups to unify the experience across devices.

## Intro
If it's worth it I'll put that which can easily be scripted into a script. For now I just want to compile the must-have pieces of my setup.


### New Machine Setup (Linux)
Terminal of choice:  
`sudo apt install terminator`  

Custom Aliases:  
```
touch ~/.bash_aliases  `
printf "\nalias git st=\"git status\"\n" >> ~/.bash_aliases 
printf "\nsource ~/.bash_aliases\n" >> ~/.bashrc
```

Git Setup:  
If setting up an SSH key to add to my github account, follow the steps [here](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).  

Then:  
```
git config --global alias.st status
git config --global alias.ci commit
git config --global alias.br branch
git config --global alias.co checkout
git config --global push.default simple
```
```
read -p "Enter Your Git Email: "  email
git config --global user.email "$email"
```
```
read -p "Enter Your Full Name: "  name
git config --global user.name "name"
```

Change terminal profile during SSH:  
```
wget -qO - http://archive.philippheckel.com/apt/Release.key | sudo apt-key add -
sudo sh -c "echo deb http://archive.philippheckel.com/apt/release/ release main > /etc/apt/sources.list.d/archive.philippheckel.com.list"
sudo apt-get update
sudo apt-get install terminator-hostwatch
```
Then add profiles that match the hostnames as desired. I.e. if I'm SSHing to `user@host`, I would add a profile named `host`.
More info [here](https://github.com/GratefulTony/TerminatorHostWatch).  



### rEFInd on Mac
A "boot coup" is when the Mac overwrites my custom boot settings. Resetting the NVRAM does this. OS updates sometimes do this.
The fix is to use the `bless` command from the Mac, as outlined in [these instructions](https://www.rodsbooks.com/refind/bootcoup.html#osx).  
