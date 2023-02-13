# Introduction

Oh-My-Posh is a tool for enriching your Powershell prompt.

Find more information about it [here](https://github.com/JanDeDobbeleer/oh-my-posh).

## Setting it up

- I prefer using [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701)

- Install oh-my-posh
  
  ```
  Install-Module posh-git -Scope CurrentUser
  Install-Module oh-my-posh -Scope CurrentUser
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
  

