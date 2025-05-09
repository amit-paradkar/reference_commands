Start ssh agent
```
eval "$(ssh-agent -s)"
```
Check if ssh key is created
```
ls ~/.ssh
```
If ssh key is notpresent then create a new one
```
ssh-keygen -t rsa_<add_more_specific> -C "your_email@example.com"
```
Add SSH Key to ssh agent
```
ssh-add ~/.ssh/<id_rsa_file_name>
```
Add ssh key to github
```
cat ~/.ssh/id_ed25519.pub
```
- Go to GitHub → Settings → SSH and GPG keys
- Click "New SSH key"
- Copy contents of public ssh key
Check how github is configured using command
```
git remote -v
```
If url is specified then change to ssh using following command
```
git remote set-url origin git@github.com:username/repo.git
```
Check github connection using ssh with following command
```
ssh -T git@github.com
```
If connection is successfull, then you are ready to push code

