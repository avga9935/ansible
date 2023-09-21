The very first step is to connect all machines with the main ubuntu machine, so the machine in which we are going to install the ansible can access to any of the instances without any issues.
Now create keys in each and every machine using SSH-KEYGEN.
Once created copy the ID_RSA.PUB from main machine and paste it on all of the machines under .SSH/authorized_keys.
Now make sure we can ssh to any machine from main machine.
Now Install ansible on main machine using  “ sudo apt install ansible “.
Now create an inventory file named as “ INVENTORY.INI “ we created this so we can enter the IP of the machines in which we want to make any changes we can add database IP as well.

Once done now create a playbook for whatever we want to send command to every machine.
Now create a file named as “ PLAYBOOK.YML “ in which we will put instructions/commands for othe machines.

Now run this playbook file using “ ansible-playbook -i inventory.ini myplaybook.yml “
We will get output like this

'''

PLAY [Example Playbook] ********************************************************

TASK [Gathering Facts] *********************************************************
ok: [172.31.39.70]

TASK [Update packages] *********************************************************
changed: [172.31.39.70]

TASK [Install Apache] **********************************************************
changed: [172.31.39.70]

TASK [Start Apache] ************************************************************

PLAY RECAP *********************************************************************

'''
