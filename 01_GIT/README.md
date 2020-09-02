# Code commit
```sh
# git remote remove origin

```

## SSH
- [AWS CodeCommit Multiple Account Config](https://gist.github.com/justinpawela/3a7056cd592d688425e59de2ef6f1da0)
- [Multiple SSH Keys settings for different github account](https://gist.github.com/jexchan/2351996)
- [Setting up SSH keys for different Git hosts in 3 min](https://medium.com/@sleonardoaugusto/multiple-ssh-keys-for-multiple-hosts-1f3cf5ce2dd1)
- https://forums.aws.amazon.com/thread.jspa?threadID=228206

```sh
ssh-keygen
/Users/robin8a/.ssh/jupiter_codecommit_rsa

cat ~/.ssh/jupiter_codecommit_rsa.pub

```


```sh
cd ~/.ssh
ls
nano config 

# Add

# CodeCommit hosts
Host jupiter
   HostName git-codecommit.us-east-1.amazonaws.com
   User APKA54FMZ4XCW4YTUYIE
   IdentityFile ~/.ssh/jupiter_codecommit_rsa

```

```sh
pwd
chmod 600 config
sh git-codecommit.us-east-1.amazonaws.com
```


git clone ssh://jupiter/v1/repos/su-jup-ss-disinfection-register
git remote add origin ssh://jupiter/v1/repos/su-jup-ss-disinfection-register