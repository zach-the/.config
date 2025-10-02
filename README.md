# My Config Files
To properly clone this into `.config`, do the following:
```
cd $HOME
echo "This is just creating backups of the relevant directories"
for d in config/*/; do b=$(basename "$d"); [ "$b" != ".git" ] && [ -d ".config/$b" ] && mv ".config/$b"{,.bak}; done
git clone git@github.com:zach-the/.config.git config
rsync -a config .config
rm -rf config
cd config && git status
```
