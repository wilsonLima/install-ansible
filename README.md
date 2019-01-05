install-ansible
=========

Role do Ansible para instalação da ferramenta Ansible em uma máquina remota.

Distribuições Suportadas pela Role
------------

- Debian Jessie ou superior.
- RedHat ou CentOS.


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.
- pip: Instala a dependência Pip, utilizada para instalar o Andible.
- ansible: Realiza a instalação do pacote Ansible, via instalador Pip.
- directory: Cria os diretórios onde ficam os playbooks, roles e outros componentes do Ansible.
- config: Realiza a configuração de pós instalação do Ansible.


Variáveis da Role 
--------------

- custom_home: Especifica a pasta dentro de /home onde ficam  os playbooks, roles e outros componentes do Ansible. Se não for passado, será utilizado a home do usuário utilizado para o SSH.
- version_ansible: Valor da versão do Ansible. O valor padrão é 2.7.4.


Example Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: servers
      roles:
         - install-ansible

Exemplo de uso da Role passando o número de versão por uma variável:

    - hosts: servers
      roles:
         - { role: install-ansible, version_ansible: "2.7.4" }

Exemplo de uso da Role passando a pasta dentro de /home onde fica o ambiente do Ansible, por uma variável:

    - hosts: servers
      roles:
         - { role: install-ansible, custom_home: "wlima/developer" }

Exemplo de Comandos
----------------

Comando para executar todas as tasks:

    ansible-playbook -i <caminho_inventario> <caminho_playbook>

Comando para executar a tag "config" (em caso de uso de tags, a tag "main" é obrigatória):

    ansible-playbook -i <caminho_inventario> <caminho_playbook> --tags "main, config"
