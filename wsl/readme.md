# WSL

---

## Windows Terminal ⏹

---

`wt.exe`/Windows Terminal cannot run commands in an existing Terminal Window. [[1]](#References). Below is a workaround for it. 

To start multiple tabs with Ubuntu's terminal and with different destinations:
1. Create a batch file, say `wsl.bat`, with following command 
2. run it in Command Prompt.  

*This will open tabs in Windows Terminal and closes the current Command Prompt Window.  
**Note:** Modify the command for respective needs.*  

`start wt nt -p "Ubuntu-20.04" -d "\\wsl$\Ubuntu-20.04\home\<user>\folder1" ; nt -p "Ubuntu-20.04" -d "\\wsl$\Ubuntu-20.04\home\<user>\folder2";`  

---

Tab Navigation shortcuts are same as that of Mac's-Terminal's/Chrome's Tab but instead of `CMD` key hit `Ctrl+Shift`  
*i.e.* `^⇧w` *for closing the terminal window.*

---

[📝 on 20211007]

When encountering *"Unable to connect to github.com"* or *"unable to resolve host address"* errors  
*(could happen when doing `wget -c https://github.com/ogham/exa/releases/download/v0.10.0/exa-linux-x86_64-v0.10.0.zip` or `git pull`)*

change `nameserver 174.23.23.1` to `nameserver 1.1.1.1` in `/etc/resolv.conf`  
additionally, add `generateResolvConf =  false` in `/etc/wsl.conf`  

## References

1. [Add support for wt.exe to run commands in an existing Terminal Window](https://github.com/microsoft/terminal/issues/4472)
1. [Windows Terminal Docs](https://docs.microsoft.com/en-us/windows/terminal/command-line-arguments?tabs=linux)
1. [Close CMD windows after Batch file execution](https://stackoverflow.com/questions/14697739/how-to-automatically-close-cmd-window-after-batch-file-execution)