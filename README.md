# Ansible playbook для установки TimeMachine (Netatalk) на Raspberry Pi (Rasberian Strench Lite)

Prerequirements:
* ansible
* homebrew

Setup:
```bash
# узнаем адрес Rpi
RPI_ADDR="$(arp -na | grep -i b8:27:eb | awk '{print $2}' | cut -c 2- | rev | cut -c 2- | rev)"
# добавляем его в хосты
echo "[raspberry]\n$RPI_ADDR" >> hosts

ansible-playbook timemachine.yml -i hosts --become
```


