1. ansible_connection=local -> other options in inventory file - SSH, winrm, docker - local can also be used when running cloud api calls that don't need SSH
2. find default modules here -> /Users/`<`username`>`/Library/Python/3.9/lib/python/site-packages/ansible/modules/
3. ansible command format: ansible `<`host-pattern`>` -i `<`inventory`>` -m `<`module`>` -a "`<`arguments`>`"
