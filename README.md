# Ansible playbook for Time Machine setup on Raspberry Pi

Ansible playbook of article ["Apple Time machine on RaspberryPI"](https://github.com/mr-bt/raspberrypi-timemachine).

Prerequirements:
* Rasberian Strench Lite (RPi)
* Ansible (host)

Usage:
```bash
# get RPi IP
RPI_ADDR="$(arp -na | grep -i b8:27:eb | awk '{print $2}' | cut -c 2- | rev | cut -c 2- | rev)"

# Add ip to hosts
echo "[raspberry]\n$RPI_ADDR" >> hosts

# run setup
ansible-playbook timemachine.yml -i hosts --become
```


