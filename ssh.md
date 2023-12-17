# SSH

## Multiple SSH Keys for different accounts 🍎

> _e.g. GITLAB and GITHUB_

---

Creates SSH key set for GITHUB,  
while doing this, save it as `id_ed25519_gh` or similar.

```bash
ssh-keygen -t ed25519 -C "gitHUBuser@account.com" 
```

---

Creates SSH key set for GITLAB  
while doing this, save it as `id_ed25519_gl` or similar.

```bash
ssh-keygen -t ed25519 -C "gitLABuser@account.com"
```

---

Start `ssh-agent`

```bash
eval `ssh-agent -s`
```

---

Add the key(s) to SSH Authentication Agent. 

```bash
ssh-add ~/.ssh/id_ed25519_gh ~/.ssh/id_ed25519_gl
```  

---

Edit the SSH Config file(or `touch ~/.ssh/config`), so that we can configure which key should be used for which domain, like below:  

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

---

`ssh-add -l` checks the keys.  
`ssh-add -D` deletes the keys. **Note❗️** Don't do this during setup.  


## References

1. [Multiple SSH Keys](https://gist.github.com/jexchan/2351996)
2. [ssh-add](https://www.ssh.com/ssh/add)
