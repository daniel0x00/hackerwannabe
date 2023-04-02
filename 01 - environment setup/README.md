# Exercise 01: environment setup

Every hacker needs a decently configured environment for work. You need to get used to change machine often, and bring with you your tools. In the past you used to have 'everything on a USB stick'. Those times are gone. Nowadays, you use Software Repositories and you store command-lines to install software on your 'github gist' (yes, google it now.). You configure your environment 'as code' with tool like `vagrant`, `docker`, `winget`, `chocolatey`, `homebrew` (for macOS) or similar. 

## Windows
- Suggestion is to use the already installed `winget` command-line utility to install any software. You access this by executing first `cmd.exe` from Start Menu.
- Install `Windows Terminal` with `winget` and using, when possible, always use `msstore` as source because `Microsoft Store` will always auto-update all software to the latest version. 
    - Example:

    ```
        winget search powershell
    ```

## macOS
- Leverage the already installed `Terminal` and if you want, configure it to look like a hacker (black screen with green letters).
- Suggestion is to install `homebrew` command-line utility to install any software. Install it from `Terminal` (visit homebrew website to know how). 
    - Example:

    ```
        brew search powershell
    ```


## Linux
You're on your own: if you're in Linux already you should be familiar with software repositories. 

## DELIVERY
This exercise does not have a delivery. Your only goal is to learn how to use, search and install software repositories like `winget` or `homebrew`. You need to know everything about searching, installing, uninstalling, upgrading and listing software installed on your computer using these tools.

Please try searching, installing and uninstalling this software: `Mozilla Firefox` with `winget` or `homebrew`. If using `winget`, please install it using `msstore` as source.

HINTS:
- Remember that you'll encounter many people that have done the same already. 
- Google examples by using the following google dorks: 

```
site:gist.github.com winget powershell
```

```
site:gist.github.com brew powershell
```