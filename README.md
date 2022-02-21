<h1 align="center">Powershell and plugins configurations</h1>
<p align="center">
    <b>Inspired by <a href="https://github.com/craftzdog/dotfiles-public">Craftzdog</a> and
        <a href="https://github.com/Neelfrost/nvim-config">Neelfrost</a> configurations.</b>
    <br />
    <b>This is a summary of the 2 configurations to save time.</b>
    <br />
    <br />
    <a><img
            alt="badge"
            src="https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white"/>
    </a>
</p>


![image-ps](img\ps.png)

## Table of Contents 

-   [Powershell 🖥](#Powershell-)
-   [Update 🚀](#update-)
-   [Features 📃](#features-)

The following instructions are for Windows (powershell). **An admin prompt is required.**

## Powershell 🖥

1. Install chocolatey.

   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
   ```

1. Install git dependencies.

   ```powershell
   choco install git.install --params "/GitAndUnixToolsOnPath /NoGitLfs /SChannel /NoShellIntegration" -y; RefreshEnv;
   ```
   
1. Download and install latest Hack font on GitHub.

   ```
   https://github.com/ryanoasis/nerd-fonts/releases/
   ```

2. Configure Windows Terminal following instructions in the video until 3:29.

   ```
   https://youtu.be/5-aK2_WwrmM?t=126
   ```

3. Install Powershell on the Microsoft Store.

   ```
   https://www.microsoft.com/store/productId/9MZ1SNWT0N5D
   ```

4. Change default shell following instructions in the video until 4:29.

   ```
   https://youtu.be/5-aK2_WwrmM?t=243
   ```
   
5. Change background color following instructions in the video until 5:43.

   ```
   https://youtu.be/5-aK2_WwrmM?t=269
   ```
   
6. Install Oh My Posh.

   ```powershell
   Install-Module posh-git -Scope CurrentUser -Force; Install-Module oh-my-posh -Scope CurrentUser -Force
   ```
   
7. Install Terminal Icons.

   ```powershell
   Install-Module -Name Terminal-Icons -Repository PSGallery -Force
   ```

8. Install z - Directory Jumper.

   ```powershell
   Install-Module -Name z -Force
   ```
   
9. Install PSReadLine.

   ```powershell
   Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck; Install-Module -Name PSFzf -Scope CurrentUser -Force
   ```
   
9. Install Fzf - Fuzzy finder.

   ```powershell
   choco install fzf
   ```

9. Make a user profile and set command aliases.

   ```powershell
   git clone https://github.com/LucasSers/dotfiles.git "$HOME\Appdata\Local\dotfiles"; cd "$HOME\Appdata\Local\dotfiles"; Copy-Item -Path ".\.config\" -Destination "$HOME" -Recurse -Confirm:$true -Force; Copy-Item -Path ".\PowerShell\Microsoft.PowerShell_profile.ps1" -Destination "$PROFILE" -Recurse -Confirm:$true -Force; cd "$HOME\.config\powershell"; Unblock-File -path ".\user_profile.ps1"; exit
   ```


## Update 🚀

1. Pull changes.

    ```powershell
    cd "$HOME\Appdata\Local\dotfiles"; git pull
    ```

2. Launch the update script:

    ```powershell
    Copy-Item -Path ".\.config\" -Destination "$HOME" -Recurse -Confirm:$true -Force; exit
    ```

## Features 📃

-   Aesthetic PowerShell prompt with Oh My Posh.
