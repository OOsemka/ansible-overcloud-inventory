# TripleO Ansible inventory file

Script is used to build ansible host file for Red Hat OpenStack Platform overcloud nodes. This should be executed from undercloud node as stack user. Copy the output of this script to /etc/ansible/hosts

This script has been tested with OSP7-OSP13. It has been fixed to support composable roles.

<b>Execution</b><br>
git clone https://github.com/OOsemka/ansible-overcloud-inventory.git <br>
cd ansible-overcloud-inventory<br>
chmod +x ansible-build-inventory<br>
./ansible-build-inventory > hosts<br>
sudo cp hosts /etc/ansible<br>
sudo sed -i 's/#host_key_checking = False/host_key_checking = False/' /etc/ansible/ansible.cfg<br>
<br>
<b>Test</b><br>
ansible all -m ping
