## ansible_playbook
``` run_playbook
$ ansible-playbook name.yml
```

``` help_run_playbook
$ ansible-playbook --help
```

```bash
$ ansible-playbook name.yml --check
		# запустить без изменений и попытаться предсказать, что будет
```

``` bash
$ ansible-playbook name.yml --diff --check
		# при изменении (небольших) файлов и шаблонов, показывать различия в этих файлах; отлично работает с --check
```

``` bash
$ ansible-playbook --syntax-check name.yml 
		#выполнить проверку синтаксиса в плейбуке, но не выполнять его
```

```bash
$ ansible-playbook -i ./inventory name.yml
		#указать путь для файла inventary
```
## ansible-lint
```bash
$ ansible-lint name-playbook.yml
		#это статический анализатор кода (линтер) для Ansible. Его главная задача — находить ошибки, недочеты и отклонения от лучших практик в Ansible Playbook и ролях до того, как вы их запустите.
```
`$ ansible-lint -L` - показать список всех правил
##
``` module_help
$ ansible-doc -l
```
