## Задание 4 — Ansible Ad-hoc
В этом задании вы будете работать с Ad-hoc коммандами.

Выполните действия и приложите скриншоты запуска команд.

1. Установите на управляемых хостах любой пакет, которого нет.
2. Проверьте статус любого, присутствующего на управляемой машине, сервиса.
3. Создайте файл с содержимым «I like Linux» по пути /tmp/netology.txt.
### Установка htop:
```ansible -i inventory.ini my_vms -m apt -a "name=htop state=present update_cache=yes" --become --ask-become-pass```
### Проверка статуса сервиса cron
```ansible -i inventory.ini my_vms -m shell -a "systemctl status cron | head -n 5" --become```
### Создание файла с содержимым «I like Linux» по пути /tmp/netology.txt
```ansible -i inventory.ini my_vms -m copy -a "dest=/tmp/netology.txt content='I like Linux'" --become```
