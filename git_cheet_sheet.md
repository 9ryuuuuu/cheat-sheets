# Git cheet sheet

## Git

- First Settings
```
git config --global user.name "name"
git config --global user.email "name"
```

## Github

### Create a git repository in local machine and upload to github.。

- Create a git folder in a local machine. 
  ```PowerShell
  $ new-item -type directory <directory_name>
  cd <directory_name>
  $ git init
  ```

- Create public/private keys
  ```PowerShell
  $ cd ~/.ssh
  $ ssh-keygen -t rsa
  # Enter the name of keys
  ```

- Set config  
  ```PowerShell
  $ cd ~/.ssh
  $ new-iem config
  ```

  Write below to ~/config
  ```PowerShell
  Host <host-name>
  HostName github.com
  IdentityFile ~/.ssh/<private key file>
  User git
  ```

- Test
  ```PowerShell
  ssh -T git@<host-name>
  ```

- Upload to git (Set remote origin)
  ```PowerShell
  cd <directory_name>
  git remote add origin git@<host-name>:<user-name>/<repository-name>.git
  # You can copy from "Code" button in github and change <host-name>
  
  # test
  git fetch
  ```

- Reference
  - [Multiple GitHub Accounts & SSH Config](https://stackoverflow.com/questions/3225862/multiple-github-accounts-ssh-config)
  - [GitHubでssh接続する手順~公開鍵・秘密鍵の生成から~](https://qiita.com/shizuma/items/2b2f873a0034839e47ce)


