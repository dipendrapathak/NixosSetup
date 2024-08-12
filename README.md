# Installation Instruction
First, download the latest [release](https://github.com/nix-community/NixOS-WSL/releases/latest).
Then open powershell, go to the Downloads directory.
```Powershell
wsl --import NixOS $env:USERPROFILE\NixOS\ nixos-wsl.tar.gz
```
This commands create a new wsl profile named "NixOS", with the directory in USERPROFILE\NixOS using the tar file you just downloaded.

Then you can log in to the wsl using:
```Powershell
wsl -d NixOS
```

Once you are in the shell copy and paste the content of the `install` file and paste it in. (Or if you want to set up ssh access and copy via ssh, then go for it)
```bash
nano install
```
After pasting and saving the file. Final command:
## for WSL
```bash
chmod +x ./install;nix-shell -p git vim --extra-experimental-features nix-command --extra-experimental-features flakes --command "./install wsl"
```
## for normal server
```bash
chmod +x ./install;nix-shell -p git vim --extra-experimental-features nix-command --extra-experimental-features flakes --command "./install home"
```
