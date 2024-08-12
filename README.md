Installation Instruction
First, download the latest release. Then open powershell, go to the Downloads directory.

wsl --import NixOS $env:USERPROFILE\NixOS\ nixos-wsl.tar.gz
This commands create a new wsl profile named "NixOS", with the directory in USERPROFILE\NixOS using the tar file you just downloaded.
Then you can log in to the wsl using:

wsl -d NixOS
Once you are in the shell copy and paste the content of the install file and paste it in. (Or if you want to set up ssh access and copy via ssh, then go for it)

nano install
After pasting and saving the file. Final command:
for WSL
chmod +x ./install;nix-shell -p git vim --extra-experimental-features nix-command --extra-experimental-features flakes --command "./install wsl"
for normal server
chmod +x ./install;nix-shell -p git vim --extra-experimental-features nix-command --extra-experimental-features flakes --command "./install home"
