# Exercise 02: basic tooling

Please install the following software on your base OS using only `winget` or `homebrew`:
- PowerShell.
- Windows Terminal (only in case of using Windows as base OS).
- Nmap.
- Git.
- Postman.
- Google Chrome.
- Greenshot.
- VirtualBox.

For `winget` installation, use (suggestion is to run `cmd.exe` as an Administrator before running these commands):

```powershell
    winget install --name 'PowerShell' --id '9MZ1SNWT0N5D' --exact --source 'msstore' --accept-package-agreements --accept-source-agreements --silent
    winget install --name 'Windows Terminal' --id '9N0DX20HK701' --exact --source 'msstore' --accept-package-agreements --accept-source-agreements --silent
    winget install --id 'Git.Git' --source 'winget' --accept-package-agreements --accept-source-agreements --silent
    winget install --id 'Postman.Postman' --source 'winget' --accept-package-agreements --accept-source-agreements --silent
    winget install --id 'Google.Chrome' --source 'winget' --accept-package-agreements --accept-source-agreements --silent
    winget install --id 'Greenshot.Greenshot' --source 'winget' --accept-package-agreements --accept-source-agreements --silent
    winget install --id 'Oracle.VirtualBox' --source 'winget' --accept-package-agreements --accept-source-agreements --silent
    winget install --id 'Microsoft.VisualStudioCode' --source 'winget' --accept-package-agreements --accept-source-agreements --silent
```

You can verify if you've installed each software by running the following command. If you get at least one record is because you've successfully installed the software.

```powershell
    winget list VirtualBox
```

![winget list VirtualBox output](./img/winget-list-VirtualBox-output.png)

## Configuration

1. Open Windows Terminal and set your default profile to `PowerShell`:

![Windows Terminal settings](./img/2023-04-02-20-43-25.png)
 
![Windows Terminal default profile](./img/2023-04-02-20-44-22.png)

2. Open Windows Terminal with PowerShell (don't confuse it with `Windows PowerShell`, which is different) and run the following command: 

```powershell
    Install-Module PSreadline -MinimumVersion 2.2.6 -Force -Scope CurrentUser
    if (Test-Path -Path ("C:\Users\$env:username\OneDrive\Documents\PowerShell\")) { [IO.File]::WriteAllBytes("C:\Users\$env:username\OneDrive\Documents\PowerShell\Microsoft.PowerShell_profile.ps1", [Convert]::FromBase64String('Y2RcDQpTZXQtUFNSZWFkTGluZU9wdGlvbiAtUHJlZGljdGlvblNvdXJjZSBIaXN0b3J5DQpTZXQtUFNSZWFkTGluZU9wdGlvbiAtUHJlZGljdGlvblZpZXdTdHlsZSBMaXN0Vmlldw0KU2V0LVBTUmVhZExpbmVLZXlIYW5kbGVyIC1LZXkgIlNoaWZ0K1RhYiIgLUZ1bmN0aW9uIEFjY2VwdE5leHRTdWdnZXN0aW9uV29yZA0KDQojIFNvbWV0aW1lcyB5b3Ugd2FudCB0byBnZXQgYSBwcm9wZXJ0eSBvZiBpbnZva2UgYSBtZW1iZXIgb24gd2hhdCB5b3UndmUgZW50ZXJlZCBzbyBmYXINCiMgYnV0IHlvdSBuZWVkIHBhcmVucyB0byBkbyB0aGF0LiAgVGhpcyBiaW5kaW5nIHdpbGwgaGVscCBieSBwdXR0aW5nIHBhcmVucyBhcm91bmQgdGhlIGN1cnJlbnQgc2VsZWN0aW9uLA0KIyBvciBpZiBub3RoaW5nIGlzIHNlbGVjdGVkLCB0aGUgd2hvbGUgbGluZS4NClNldC1QU1JlYWRMaW5lS2V5SGFuZGxlciAtS2V5ICdBbHQrKCcgYA0KICAgICAgICAgICAgICAgICAgICAgICAgIC1CcmllZkRlc2NyaXB0aW9uIFBhcmVudGhlc2l6ZVNlbGVjdGlvbiBgDQogICAgICAgICAgICAgICAgICAgICAgICAgLUxvbmdEZXNjcmlwdGlvbiAiUHV0IHBhcmVudGhlc2lzIGFyb3VuZCB0aGUgc2VsZWN0aW9uIG9yIGVudGlyZSBsaW5lIGFuZCBtb3ZlIHRoZSBjdXJzb3IgdG8gYWZ0ZXIgdGhlIGNsb3NpbmcgcGFyZW50aGVzaXMiIGANCiAgICAgICAgICAgICAgICAgICAgICAgICAtU2NyaXB0QmxvY2sgew0KICAgIHBhcmFtKCRrZXksICRhcmcpDQoNCiAgICAkc2VsZWN0aW9uU3RhcnQgPSAkbnVsbA0KICAgICRzZWxlY3Rpb25MZW5ndGggPSAkbnVsbA0KICAgIFtNaWNyb3NvZnQuUG93ZXJTaGVsbC5QU0NvbnNvbGVSZWFkTGluZV06OkdldFNlbGVjdGlvblN0YXRlKFtyZWZdJHNlbGVjdGlvblN0YXJ0LCBbcmVmXSRzZWxlY3Rpb25MZW5ndGgpDQoNCiAgICAkbGluZSA9ICRudWxsDQogICAgJGN1cnNvciA9ICRudWxsDQogICAgW01pY3Jvc29mdC5Qb3dlclNoZWxsLlBTQ29uc29sZVJlYWRMaW5lXTo6R2V0QnVmZmVyU3RhdGUoW3JlZl0kbGluZSwgW3JlZl0kY3Vyc29yKQ0KICAgIGlmICgkc2VsZWN0aW9uU3RhcnQgLW5lIC0xKQ0KICAgIHsNCiAgICAgICAgW01pY3Jvc29mdC5Qb3dlclNoZWxsLlBTQ29uc29sZVJlYWRMaW5lXTo6UmVwbGFjZSgkc2VsZWN0aW9uU3RhcnQsICRzZWxlY3Rpb25MZW5ndGgsICcoJyArICRsaW5lLlN1YlN0cmluZygkc2VsZWN0aW9uU3RhcnQsICRzZWxlY3Rpb25MZW5ndGgpICsgJyknKQ0KICAgICAgICBbTWljcm9zb2Z0LlBvd2VyU2hlbGwuUFNDb25zb2xlUmVhZExpbmVdOjpTZXRDdXJzb3JQb3NpdGlvbigkc2VsZWN0aW9uU3RhcnQgKyAkc2VsZWN0aW9uTGVuZ3RoICsgMikNCiAgICB9DQogICAgZWxzZQ0KICAgIHsNCiAgICAgICAgW01pY3Jvc29mdC5Qb3dlclNoZWxsLlBTQ29uc29sZVJlYWRMaW5lXTo6UmVwbGFjZSgwLCAkbGluZS5MZW5ndGgsICcoJyArICRsaW5lICsgJyknKQ0KICAgICAgICBbTWljcm9zb2Z0LlBvd2VyU2hlbGwuUFNDb25zb2xlUmVhZExpbmVdOjpFbmRPZkxpbmUoKQ0KICAgIH0NCn0NCg0KIyBQcm9tcHQgY2hhbmdlOg0KZnVuY3Rpb24gcHJvbXB0IHsgV3JpdGUtSG9zdCAiUFMgJCgkUFdELlByb3ZpZGVyUGF0aClgbj4gIiAtTm9OZXdsaW5lIC1Gb3JlZ3JvdW5kQ29sb3IgRGFya0dyYXk7IHJldHVybiAiICIgfSA=')) } `
    elseif (Test-Path -Path ("C:\Users\$env:username\Documents\PowerShell\")) { [IO.File]::WriteAllBytes("C:\Users\$env:username\Documents\PowerShell\Microsoft.PowerShell_profile.ps1", [Convert]::FromBase64String('Y2RcDQpTZXQtUFNSZWFkTGluZU9wdGlvbiAtUHJlZGljdGlvblNvdXJjZSBIaXN0b3J5DQpTZXQtUFNSZWFkTGluZU9wdGlvbiAtUHJlZGljdGlvblZpZXdTdHlsZSBMaXN0Vmlldw0KU2V0LVBTUmVhZExpbmVLZXlIYW5kbGVyIC1LZXkgIlNoaWZ0K1RhYiIgLUZ1bmN0aW9uIEFjY2VwdE5leHRTdWdnZXN0aW9uV29yZA0KDQojIFNvbWV0aW1lcyB5b3Ugd2FudCB0byBnZXQgYSBwcm9wZXJ0eSBvZiBpbnZva2UgYSBtZW1iZXIgb24gd2hhdCB5b3UndmUgZW50ZXJlZCBzbyBmYXINCiMgYnV0IHlvdSBuZWVkIHBhcmVucyB0byBkbyB0aGF0LiAgVGhpcyBiaW5kaW5nIHdpbGwgaGVscCBieSBwdXR0aW5nIHBhcmVucyBhcm91bmQgdGhlIGN1cnJlbnQgc2VsZWN0aW9uLA0KIyBvciBpZiBub3RoaW5nIGlzIHNlbGVjdGVkLCB0aGUgd2hvbGUgbGluZS4NClNldC1QU1JlYWRMaW5lS2V5SGFuZGxlciAtS2V5ICdBbHQrKCcgYA0KICAgICAgICAgICAgICAgICAgICAgICAgIC1CcmllZkRlc2NyaXB0aW9uIFBhcmVudGhlc2l6ZVNlbGVjdGlvbiBgDQogICAgICAgICAgICAgICAgICAgICAgICAgLUxvbmdEZXNjcmlwdGlvbiAiUHV0IHBhcmVudGhlc2lzIGFyb3VuZCB0aGUgc2VsZWN0aW9uIG9yIGVudGlyZSBsaW5lIGFuZCBtb3ZlIHRoZSBjdXJzb3IgdG8gYWZ0ZXIgdGhlIGNsb3NpbmcgcGFyZW50aGVzaXMiIGANCiAgICAgICAgICAgICAgICAgICAgICAgICAtU2NyaXB0QmxvY2sgew0KICAgIHBhcmFtKCRrZXksICRhcmcpDQoNCiAgICAkc2VsZWN0aW9uU3RhcnQgPSAkbnVsbA0KICAgICRzZWxlY3Rpb25MZW5ndGggPSAkbnVsbA0KICAgIFtNaWNyb3NvZnQuUG93ZXJTaGVsbC5QU0NvbnNvbGVSZWFkTGluZV06OkdldFNlbGVjdGlvblN0YXRlKFtyZWZdJHNlbGVjdGlvblN0YXJ0LCBbcmVmXSRzZWxlY3Rpb25MZW5ndGgpDQoNCiAgICAkbGluZSA9ICRudWxsDQogICAgJGN1cnNvciA9ICRudWxsDQogICAgW01pY3Jvc29mdC5Qb3dlclNoZWxsLlBTQ29uc29sZVJlYWRMaW5lXTo6R2V0QnVmZmVyU3RhdGUoW3JlZl0kbGluZSwgW3JlZl0kY3Vyc29yKQ0KICAgIGlmICgkc2VsZWN0aW9uU3RhcnQgLW5lIC0xKQ0KICAgIHsNCiAgICAgICAgW01pY3Jvc29mdC5Qb3dlclNoZWxsLlBTQ29uc29sZVJlYWRMaW5lXTo6UmVwbGFjZSgkc2VsZWN0aW9uU3RhcnQsICRzZWxlY3Rpb25MZW5ndGgsICcoJyArICRsaW5lLlN1YlN0cmluZygkc2VsZWN0aW9uU3RhcnQsICRzZWxlY3Rpb25MZW5ndGgpICsgJyknKQ0KICAgICAgICBbTWljcm9zb2Z0LlBvd2VyU2hlbGwuUFNDb25zb2xlUmVhZExpbmVdOjpTZXRDdXJzb3JQb3NpdGlvbigkc2VsZWN0aW9uU3RhcnQgKyAkc2VsZWN0aW9uTGVuZ3RoICsgMikNCiAgICB9DQogICAgZWxzZQ0KICAgIHsNCiAgICAgICAgW01pY3Jvc29mdC5Qb3dlclNoZWxsLlBTQ29uc29sZVJlYWRMaW5lXTo6UmVwbGFjZSgwLCAkbGluZS5MZW5ndGgsICcoJyArICRsaW5lICsgJyknKQ0KICAgICAgICBbTWljcm9zb2Z0LlBvd2VyU2hlbGwuUFNDb25zb2xlUmVhZExpbmVdOjpFbmRPZkxpbmUoKQ0KICAgIH0NCn0NCg0KIyBQcm9tcHQgY2hhbmdlOg0KZnVuY3Rpb24gcHJvbXB0IHsgV3JpdGUtSG9zdCAiUFMgJCgkUFdELlByb3ZpZGVyUGF0aClgbj4gIiAtTm9OZXdsaW5lIC1Gb3JlZ3JvdW5kQ29sb3IgRGFya0dyYXk7IHJldHVybiAiICIgfSA=')) } `
    else { "No PowerShell folder detected." }
```

3. Install VSCode useful extensions

Open Windows Terminal and paste this, which will install useful VSCode Extensions to be used during the course:

```cmd
    code --install-extension arcsector.vscode-splunk-search-syntax
    code --install-extension csholmq.excel-to-markdown-table
    code --install-extension ms-vscode.powershell
    code --install-extension mushan.vscode-paste-image
    code --install-extension shd101wyy.markdown-preview-enhanced
    code --install-extension streetsidesoftware.code-spell-checker
    code --install-extension TakumiI.markdowntable
    code --install-extension yzhang.markdown-all-in-one
```

## Possible errors

If you find you don't have installed `winget`, open Microsoft Store for the first time and it should get installed automatically. Then, just try again.

![](./img/2023-04-10-10-26-27.png)