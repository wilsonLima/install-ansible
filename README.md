install-ansible
=========

Role do Ansible para instalação da ferramenta Ansible em uma máquina remota.

Distribuições Suportadas pela Role
------------

- Debian Jessie ou superior.
- RedHat ou CentOS.
- Fedora 29 ou superior
- Linux Mint 18 ou superior
- openSUSE Leap 15.0 ou superior
- openSUSE Tumbleweed
- Ubuntu 18.10 ou superior


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.
- deps: Instala as dependências essenciais para o Ansible.
- repo: Adiciona os repositórios do Ansible.
- ansible: Realiza a instalação do pacote Ansible, via instalador Pip.
- directory: Cria os diretórios onde ficam os playbooks, roles e outros componentes do Ansible.
- config: Realiza a configuração de pós instalação do Ansible.


Variáveis da Role 
--------------

- custom_home: Especifica a pasta dentro de /home onde ficam  os playbooks, roles e outros componentes do Ansible. Se não for passado, será utilizado a home do usuário utilizado para o SSH.


Example Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: servers
      roles:
         - install-ansible

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


License
-------

MIT License