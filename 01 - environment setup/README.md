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

## Environment going forward
This course will assume you are using Windows as base OS, however, you shouldn't find problems to use macOS or Linux as base OS as all software used will be cross-OS compatible. 

If you are using macOS, it is recommended you install VirtualBox software (via `homebrew` or direct website download) and use a virtualized Windows 11 image. You can download Windows 11 ISO [here](https://www.microsoft.com/software-download/windows11), section "Download Windows 11 Disk Image (ISO) for x64 devices". You can use this ISO to install Windows 11 as guest OS and thus continue this course in there. We will learn this later on the course, but you can stretch searching on YouTube "[how to install Windows 11 from Mac using VirtualBox](https://www.youtube.com/watch?v=vxxEGiMR4sw)".


## DELIVERY
Your goal is to learn how to use, search and install software using repositories like `winget` or `homebrew`. You need to know everything about searching, installing, listing, uninstalling, and upgrading software installed on your computer using these tools.

Please:
1. Install this software: `Mozilla Firefox` with `winget` or `homebrew`.
2. If using `winget`, please install it using `msstore` as source.
3. Enumerate installed software using `winget` or `homebrew`. 
4. Uninstall `Mozilla Firefox` using `winget` or `homebrew`.
5. Repeat the installation but using `silent approach` (to avoid popups and license agreements). 

Hints:
- Remember that you'll encounter many people that have done the same already. 
- Google examples by using the following google dork `site:gist.github.com <your question>`.
- Use `winget --help` and `winget install --help` to get help.
- `winget` parameters you will use: `--id`, `--source`, `--accept-package-agreements`, `--accept-source-agreements` and `--silent`. 

This exercise does not have a delivery. 