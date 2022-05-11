## Установка clickhouse и vector

Данный playbook:
 - Устанавливает clichouse
 - Устанавливает vector
 - Запускает службу clichouse-server
 - Запускает службу vector
 - Создает базу `logs` в clichouse 

Для работы playbook необходимо:
 - Добавить ip-адрес сервера в [inventory](./src/playbook/inventory/prod.yml) файл
 - Указать имя пользователя в [inventory](./src/playbook/inventory/prod.yml) файле
 - В файлах [vars](./src/playbook/group_vars/)'ов указать необходимые версии дистрибутивов. Их можно посмотреть на официальных сайтах [clichouse](https://packages.clickhouse.com/rpm/stable/) и [vector](https://packages.timber.io/vector/)
 - Скопировать свой публичный ssl ключ на удаленный сервер
```bash
$ ssh-copy-id -i ~/.ssh/id_rsa.pub root@192.168.1.216
```
 - Запустить playbook:
```bash
$ ansible-playbook -i inventory/prod.yml site.yml
```
