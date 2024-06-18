```ansible

$ sudo apt-add-repository -y ppa:ansible/ansible
$ sudo apt-get update
$ sudo apt-get install -y ansible

$ sudo apt-get install software-properties-common

ip of vps @host.ini or 
/etc/ansible/hosts

ansible -i hosts.ini example -m ping 

If you insist on using passwords, add the --ask-pass (-k) flag to Ansible
commands (you may also need to install the sshpass package for this to
work)

vagrant box add geerlingguy/rockylinux8
vagrant init geerlingguy/rockylinux8
vagrant up

---
- hosts: all
become: yes
tasks:
- name: Ensure chrony (for time synchronization) is installed.
dnf:
name: chrony
state: present
- name: Ensure chrony is running.
service:
name: chronyd
state: started
enabled: yes

-->
A shell script with the same effect would
be:
# Start chronyd if it's not already running.
if ps aux | grep -q "[c]hronyd"
then
echo "chronyd is running." > /dev/null
else
systemctl start chronyd.service > /dev/null
echo "Started chronyd."
fi
# Make sure chronyd is enabled on system startup.
systemctl enable chronyd.service






















```