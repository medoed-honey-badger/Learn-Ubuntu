# Всякие мыслишки:
1. Описать, как отключать доступ по паролю
2. Как настраивать SSH
    - https://selectel.ru/blog/tutorials/how-to-generate-ssh/
    - https://selectel.ru/blog/ssh-keys/
    - https://phoenixnap.com/kb/ssh-to-connect-to-remote-server-linux-or-windows#ftoc-heading-8
    - https://phoenixnap.com/kb/ssh-with-key
    - Попадаем в папку `/home/<имя пользователя>`
    - проверяем своими шарами, что папки _.ssh_ не существует, с помощью `ls -a`
    - `sudo mkdir .ssh`
    - `cd .ssh`
    - `sudo nano authorized_keys`
        - Перенёс в него данные из публичного ключа
3. Как можно поймать майнер
4. Как узнать, какие ещё есть доступные аргументы для команд
    - `--help`, `-h`
         - краткая форма бывает иногда занята...
         - Например у той же `ls` -  `-h`, `--human-readable` - with -l and -s, print sizes like 1K 234M 2G etc.
6. Как создавать пользователя и зачем
    - `sudo useradd -m <имя пользователя>`
        - `-m`, `--create-home` - create the user's home directory
        - Есть `-p`, `--password PASSWORD` - encrypted password of the new account
            - То есть можно при создании пользователя ему сразу и пароль навесить
        - -s, --shell SHELL             login shell of the new account
            - Скорее всего сразу на его консоль и переключиться можно
    - ? есть ли другие команды
    - ? зачем создавать нового пользователя
        - > Do not run steamcmd while operating as the root user. Doing so is a security risk.
            - https://developer.valvesoftware.com/wiki/SteamCMD#Linux
    - лучше добавляй так:
        `adduser user` from Tevdore at Telegram
7. Удаление пользователя
    - `sudo deluser --remove-home your_user`
        - https://askubuntu.com/a/1013603
8. Установка пароля для пользователя
   - `sudo passwd <имя пользователя>`
9. Как изменять права
    - `sudo adduser <имя пользователя> sudo`
        - https://askubuntu.com/a/1414685
    - `sudo` - get root previges
    - `adduser` - used for adding users and adding user to groups for more info run `adduser --help`
    - `<название пользователя>` the user to add to the group
    - `sudo` - the group to add the user
    - СУДЯ ПО ВСЕМУ ПРАВА НАДО МЕНЯТЬ ДЛЯ ВСЕХ СОЗДАННЫХ ПОЛЬЗОВАТЕЛЕЙ, иначе можно получать ошибку `<имя пользователя> is not in the sudoers file.`
    - выдавать судо так:
        `sudo usermod -aG sudo user` from Tevdore at Telegram
10. Как проверять, какие права установлены
    - `ls -l ~/.ssh/`
        - **TODO** Выяснить, что значат эти команды
11. Как удалить папку и файлы внутри
    - `rm -rf <название папки>`
    - ? что означают каждая из команд
        - `rm` - скорее всего сокращение от слова **remove**
    - https://rebrainme.com/blog/linux/kak-udalyat-fajly-i-direktorii-v-linux/
12. Как выполнить команду из под конкретного пользователя
    - `sudo -u <имя пользователя> {команда}`
         - `-u`, `--user=user` - run command (or edit file) as specified user name or ID
     - Например `sudo -u <имя пользователя> -s` запустит терминал(shell) из под этого пользователя
         - `-s`, `--shell` - run shell as the target user; a command may also be specified
13. Установка приложений(application)
    - `apt-get`
    - 
14. Если название файла начинается с точки, то это значит, что он скрытый
    - Почерпнул отсюда - https://www.youtube.com/watch?v=I4ff1HCrpsg
15. Перезагрузка сервера при сообщении "System restart required"
    - `sudo reboot`
    - https://askubuntu.com/questions/258297/should-i-always-restart-the-system-when-i-see-system-restart-required
16. Если используется _sh_ вместо **bash** --- from Tevdore at Telegram
    - `echo $0` на выходе будет **-sh**
    - `sudo cat /etc/sudoers`
    - `cat /etc/passwd` и смотрим в конце строки, какая у пользователя shell
        - Например `armarserver:x:1000:1000::/home/armarserver:/bin/sh`
    - Меняем на bash с помощью `sudo visudo /etc/passwd`
17. `tmux`
    - https://tmuxcheatsheet.com/
18. Обновление системы - https://askubuntu.com/a/196777
    - `sudo apt update`
    - `sudo apt upgrade`
    - И в конце `sudo reboot now`


## Файловая система:
1. `lsblk` - Посмотреть, сколько всего места на диске
    - `df -h` - покажет, сколько места реально занято/свободно на смонтированных разделах
2. `sudo vgs`
    - Проверить, сколько свободного места в Volume Group
3. 


Узнал отсюда - https://www.youtube.com/watch?v=qwopGsaNF_Q:
1. `pwd` - для показа текущей директории - Present Working Directory
2. `cd ~` - переход к домашней директории
3. 

https://www.youtube.com/watch?v=PvBp7tRgQV4:
1. `cd -` - переход к предыдущей директории
2. `Ctrl + A` | `Ctrl + E` - переход к началу/концу строки. Если вдруг не фурычат Home и End

# Почитать
1. https://www.pathname.com/fhs/pub/fhs-2.3.html
2. https://www.tutorialspoint.com/unix/what-is-linux.htm
3. https://phoenixnap.com/glossary/what-is-root-access
4. https://phoenixnap.com/kb/touch-command-in-linux
5. https://wiki.archlinux.org/title/Systemd#Basic_systemctl_usage
6. 

# Видео:
1. [Linux VDS/VPS. KVM and OpenVZ virtualization. Create Website, Game Server, graphical VNC access | Pingvinus](https://www.youtube.com/watch?v=HX0LN3Zpovk)
2. [Linux для начинающих / Урок #1 – Что такое дистрибутивы, Bash Shell и Ubuntu? | Гоша Дударь](https://www.youtube.com/watch?v=fE1VG1gpXjU)
3. [Основные команды Linux терминала (Ubuntu, Linux Mint, Debian) | Konstantin Severin](https://www.youtube.com/watch?v=od9q1ReDdOA)
4. 


# Инструменты для Windows
1. https://www.xshell.com/en/free-for-home-school/
2. 
