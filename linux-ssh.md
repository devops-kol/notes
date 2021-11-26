
## ** SSH **


**1. Создание ключей SSH**

- команда для создания ключа
`ssh-keygen`

- публичный ключ раскидываем по всем нужным серверам

- импорт публичного ключа на удаленный серверам (2 варианта)

`ssh-copy-id -i .ssh/id_rsa.pub root@192.168.0.2`

`cat .ssh/id_rsa.pub | ssh root@192.168.0.2 'cat >> .ssh/authorized_keys' `


**2. Безопасность SSH**

`vim /etc/ssh/sshd_config` - открываем конфиг SSH

`Port > 1024` - меняем значение Port

`PubkeyAuthentication yes` - устанавливаем вход по ключу

`PermitEmptyPasswords no` - отключение авторизации по паролю

`PermitRootLogin no` - запрет авторизации пользователя root

`AllowUsers User1 User2` - разрешение на подключение конкретных пользователей

`service sshd restart` - перезапускаем SSH


**3. Настройки для каждого хоста**

- файл конфигурации
`vim .ssh/config`

- содержимое конфиг файла
```
Host 192.168.0.*
Port > 1024
User support
IdentityFile ~/.ssh/id_topsecretkey
BatchMode yes
```

**4. Авторизация по ключу на удаленном сервере по кастомному порту**

`ssh -i '~/.ssh/id_divinity' -p 1861 freeman@myownvds.ru`




