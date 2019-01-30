# ansible_base

Para realizar un ping:
- ansible -i inventories/hosts.ini all -m ping

Instalar dependencias:
- ansible-galaxy install -r config/requirements.yml

Lanzar playbook:
- ansible-playbook -i inventories/hosts.ini main.yml --become
