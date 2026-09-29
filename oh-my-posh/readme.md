# Introduction

Oh-My-Posh is a tool for enriching your Powershell prompt.

Find more information about it [here](https://github.com/JanDeDobbeleer/oh-my-posh).

## Setting it up

- I prefer using [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701)

- Install the TerminalIcons Powershell module:

  ```
  Install-Module -Name Terminal-Icons -Repository PSGallery -Scope CurrentUser
  ```

- Install oh-my-posh

  Oh-My-Posh is no longer a Powershell module, but a standalone executable.
  Install it via winget using this command:
  
  ```
  winget install JanDeDobbeleer.OhMyPosh --source winget
  ```

- Install the `PSReadline` extension

  ```
  Install-Module -Name PSReadLine -AllowPrerelease -Scope CurrentUser -Force -SkipPublisherCheck
  ```

- Install a font that supports glyphs
  For instance [Cascadia-Code](https://github.com/microsoft/cascadia-code/releases)

- In Windows Terminal, configure this font.  

- Open your profile (`code $profile`) and put in these lines:

  ```
  Import-Module posh-git
  Import-Module -Name Terminal-Icons
  Import-Module PSReadLine
  Set-PSReadLineOption -PredictionSource History
  Set-PSReadLineOption -PredictionViewStyle ListView
  Set-PSReadLineOption -EditMode Windows
  oh-my-posh --init --shell pwsh --config $env:OneDriveConsumer\settings\default_settings.omp.json | Invoke-Expression
  ```

  In the last line, I'm referring to the oh-my-posh template that I want to use.  I've placed the file on my one-drive so that I can easily use it accross all workstations that I would have.
  The file is also present in this repository.

## More information

To setup Oh-My-Posh, I've based myself on the excellent blogposts of Scott Hanselmann regarding this topic:

- [Pretty prompt in Windows Terminal](https://www.hanselman.com/blog/how-to-make-a-pretty-prompt-in-windows-terminal-with-powerline-nerd-fonts-cascadia-code-wsl-and-ohmyposh)
- [Predictive intellisense with PSReadline](https://www.hanselman.com/blog/adding-predictive-intellisense-to-my-windows-terminal-powershell-prompt-with-psreadline)
  

