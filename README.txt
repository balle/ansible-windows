# ansible-windows-laptop setup

Install Cygwin including packaes for ansible and git.
Afterwards install the optional Windows Feature for OpenSSH-Server
Edit C:\ProgramData\ssh\sshd_config and set ListenAddress 127.0.0.1
In Powershell type the following to start the server

Start-Service -Name "sshd"

Set-Service -Name "sshd" -StartupType Automatic

Afterwards try to connect to it 

ssh user@localhost 

In the Cygwin terminal clone the Git repository using an auth key

cd /etc
mv ansible ansible-orig
git clone <url_to_this_repo> ansible
cd /etc/ansible

Make sure the correct user is in hosts and playbook file.

To install development environment run
ansible-playbook --ask-pass --ask-vault-pass playbook.yml
