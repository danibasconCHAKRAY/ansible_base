# ansible_base

La primera vez debes configurar un entorno para tu playbook. Este entorno de contendrá las dependencias (en sus versiones) necesarias para la ejecución del playbook.

- virtualenv .packages
- source .packages/bin/activate
- pip install -r requirements.txt

Definimos las variables del sistema que nos servirá para establecer el entorno y la configuración base de ansible.

- export ANSIBLE_CONFIG=ansible.cfg

Instalamos los roles dependientes.
- ansible-galaxy install -r inventories/roles.yml

Para realizar un ping:
- ansible -i inventories/hosts.ini all -m ping

Lanzar playbook:
- ansible-playbook main.yml --become
