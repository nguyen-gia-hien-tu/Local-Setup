# Installing Tools for Development in WSL

## Install `wslu` and Configure to Open Web Browser

When a command-line tool (like GitHub CLI `gh`) attempts to automatically open
a web browser but cannot find an appropriate executable in your system's `PATH`,
you will encounter the error

```bash
exec: "xdg-open,x-www-browser,www-browser,wslview": executable file not found in $PATH
```

To fix the issue, you need to install the `wslu` package, which provides the
`wslview` command to bridge the Linux environment with the Windows host's
browser

To install `wslu`, follow the below steps:

- First, you might need to add the `wslu` PPA (Personal Package Archive) with

  ```bash
  sudo add-apt-repository ppa:wslutilities/wslu
  ```

- Then, install `wslu` package with

  ```bash
  sudo apt update
  sudo apt install wslu
  ```

> [!NOTE]
> When trying to use tools (like GitHub CLI `gh`) to connect to the web browser,
you might encounter an issue saying
>
> ```bash
> exec: "xdg-open,x-www-browser,www-browser,wslview": executable file not found in $PATH
> ```
>
> To resolve the issue, run the fixing script with the following command
>
> ```powershell
> Invoke-Expression (Invoke-RestMethod -Uri "https://gist.githubusercontent.com/emilwojcik93/6f337453a482f15dde4959d0b032ae0e/raw/Fix-WSLInterop.ps1") -Verbose
> ```
>
> - Make sure you're running PowerShell as Administrator (required for WSL modifications)
> - Your execution policy might need to allow scripts. If needed, run:
>
>   ```powershell
>   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
>   ```
>
> - This script requires WSL 2 with an Ubuntu-based distribution installed
