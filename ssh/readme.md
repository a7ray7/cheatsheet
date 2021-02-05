# SSH

## Multiple SSH Keys for different accounts

e.g. GITLAB and GITHUB

`ssh-keygen -t ed25519 -C "gitHUBuser@account.com"` creates SSH key set for GITHUB,  
while doing this save it as `id_ed25519_gh` or similar

`ssh-keygen -t ed25519 -C "gitLABuser@account.com"` creates SSH key set for GITLAB  
while doing this save it as `id_ed25519_gl` or similar

`ssh-add ~/.ssh/id_ed25519_gh` adds the key to SSH Authentication Agent  
`ssh-add ~/.ssh/id_ed25519_gl`  

`ssh-add -l` checks the keys  
`ssh-add -D` deletes the keys  

Edit the SSH Config file, so that we can configure which key should be used for which domain, like below:  

```bash
# Gitlab
Host gitlab.com
    Hostname gitlab.com
    User git
    IdentityFile ~/.ssh/id_ed25519_gl

# Github
Host github.com
    Hostname github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_gh
```

## References

1. [Multiple SSH Keys](https://gist.github.com/jexchan/2351996)
2. [ssh-add](https://www.ssh.com/ssh/add)
