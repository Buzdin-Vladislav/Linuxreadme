To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

vlad@vlad-VirtualBox:~$ sudo  useradd -s
[sudo] пароль для vlad: 
useradd: ключ должен использоваться с аргументом — «s»
Использование: useradd [параметры] ПОЛЬЗОВАТЕЛЬ
               useradd -D
               useradd -D [параметры]

Параметры:
      --badnames                do not check for bad names
  -b, --base-dir БАЗ_КАТ        базовый каталог для домашнего каталога новой
                                учётной записи
      --btrfs-subvolume-home    use BTRFS subvolume for home directory
  -c, --comment КОММЕНТАРИЙ     поле GECOS новой учётной записи
  -d, --home-dir ДОМ_КАТ        домашний каталог новой учётной записи
  -D, --defaults                показать или изменить настройки
                                по умолчанию для useradd
  -e, --expiredate ДАТА_УСТ     дата устаревания новой учётной записи
  -f, --inactive НЕАКТИВНОСТЬ   период неактивности пароля новой учётной записи
  -g, --gid ГРУППА              имя или ID первичной группы новой
                                учётной записи
  -G, --groups ГРУППЫ           список дополнительных групп новой
                                учётной записи
  -h, --help                    показать данное сообщение и закончить работу
  -k, --skel КАБ_ШАБ            использовать альтернативный каталог с шаблонами
  -K, --key КЛЮЧ=ЗНАЧЕНИЕ       заменить значение по умолчанию
                                из /etc/login.defs
  -l, --no-log-init             не добавлять пользователя в базы данных lastlog и
                                faillog
  -m, --create-home             создать домашний каталог пользователя
  -M, --no-create-home          не создавать домашний каталог пользователя
  -N, --no-user-group           не создавать группу с тем же именем что и у
                                пользователя
  -o, --non-unique              разрешить создание пользователей с
                                повторяющимися (не уникальными) UID
  -p, --password ПАРОЛЬ         зашифрованный пароль новой учётной записи
  -r, --system                  создавать системную группу
  -R, --root КАТ_CHROOT         каталог, в который выполняется chroot
  -P, --prefix PREFIX_DIR       prefix directory where are located the /etc/* files
  -s, --shell ОБОЛОЧКА          регистрационная оболочка новой
                                учётной записи
  -u, --uid UID                 пользовательский ID новой учётной записи
  -U, --user-group              создать группу с тем же именем что и у
                                пользователя
  -Z, --selinux-user SEUSER     использовать указанного SEUSER для
                                пользовательского сопоставления SELinux
      --extrausers              Use the extra users database

vlad@vlad-VirtualBox:~$ sudo adduser user1
Добавляется пользователь «user1» ...
Добавляется новая группа «user1» (1001) ...
Добавляется новый пользователь «user1» (1001) в группу «user1» ...
Создаётся домашний каталог «/home/user1» ...
Копирование файлов из «/etc/skel» ...
Новый пароль: 
НЕУДАЧНЫЙ ПАРОЛЬ: Пароль не прошел проверку орфографии - слишком простой
Повторите ввод нового пароля: 
Извините, но пароли не совпадают.
Новый пароль: 
Повторите ввод нового пароля: 
passwd: пароль успешно обновлён
Изменение информации о пользователе user1
Введите новое значение или нажмите ENTER для выбора значения по умолчанию
	Полное имя []: vlad
	Номер комнаты []: 1
	Рабочий телефон []: 1
	Домашний телефон []: 1
	Другое []: 1
Данная информация корректна? [Y/n] y
vlad@vlad-VirtualBox:~$ tail /ect/passwd
tail: невозможно открыть '/ect/passwd' для чтения: Нет такого файла или каталога
vlad@vlad-VirtualBox:~$ tail /etc/passwd
nm-openvpn:x:121:127:NetworkManager OpenVPN,,,:/var/lib/openvpn/chroot:/usr/sbin/nologin
saned:x:122:129::/var/lib/saned:/usr/sbin/nologin
colord:x:123:130:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
geoclue:x:124:131::/var/lib/geoclue:/usr/sbin/nologin
pulse:x:125:132:PulseAudio daemon,,,:/run/pulse:/usr/sbin/nologin
gnome-initial-setup:x:126:65534::/run/gnome-initial-setup/:/bin/false
hplip:x:127:7:HPLIP system user,,,:/run/hplip:/bin/false
gdm:x:128:134:Gnome Display Manager:/var/lib/gdm3:/bin/false
vlad:x:1000:1000:vlad,,,:/home/vlad:/bin/bash
user1:x:1001:1001:vlad,1,1,1,1:/home/user1:/bin/bash
vlad@vlad-VirtualBox:~$ sudo tail /etc/shadow
nm-openvpn:*:19411:0:99999:7:::
saned:*:19411:0:99999:7:::
colord:*:19411:0:99999:7:::
geoclue:*:19411:0:99999:7:::
pulse:*:19411:0:99999:7:::
gnome-initial-setup:*:19411:0:99999:7:::
hplip:*:19411:0:99999:7:::
gdm:*:19411:0:99999:7:::
vlad:$y$j9T$1H/onkxg0NUprh4BQR7Ns1$EgyLhrUgXY078UHTjZrp1C2AjaaD7fwwyNKHNmztd8/:19501:0:99999:7:::
user1:$y$j9T$Bfy8DCCX5IIweKJzJTVv00$vbrAFkqQWUboZafqTGeERPhRbxxmYP3gEsqJylVER08:19501:0:99999:7:::
vlad@vlad-VirtualBox:~$ sudo apt-get install ssh
[sudo] пароль для vlad: 
Попробуйте ещё раз.
[sudo] пароль для vlad: 
Чтение списков пакетов… Готово
Построение дерева зависимостей… Готово
Чтение информации о состоянии… Готово         
Будут установлены следующие дополнительные пакеты:
  ncurses-term openssh-server openssh-sftp-server ssh-import-id
Предлагаемые пакеты:
  molly-guard monkeysphere ssh-askpass
Следующие НОВЫЕ пакеты будут установлены:
  ncurses-term openssh-server openssh-sftp-server ssh ssh-import-id
Обновлено 0 пакетов, установлено 5 новых пакетов, для удаления отмечено 0 пакетов, и 174 пакетов не обновлено.
Необходимо скачать 755 kB архивов.
После данной операции объём занятого дискового пространства возрастёт на 6 179 kB.
Хотите продолжить? [Д/н] д
Пол:1 http://ru.archive.ubuntu.com/ubuntu jammy-updates/main amd64 openssh-sftp-server amd64 1:8.9p1-3ubuntu0.1 [38,7 kB]
Пол:2 http://ru.archive.ubuntu.com/ubuntu jammy-updates/main amd64 openssh-server amd64 1:8.9p1-3ubuntu0.1 [434 kB]
Пол:3 http://ru.archive.ubuntu.com/ubuntu jammy-updates/main amd64 ssh all 1:8.9p1-3ubuntu0.1 [4 850 B]
Пол:4 http://ru.archive.ubuntu.com/ubuntu jammy-updates/main amd64 ncurses-term all 6.3-2ubuntu0.1 [267 kB]
Пол:5 http://ru.archive.ubuntu.com/ubuntu jammy/main amd64 ssh-import-id all 5.11-0ubuntu1 [10,1 kB]
Получено 755 kB за 6с (125 kB/s)                                                                    
Предварительная настройка пакетов …
Выбор ранее не выбранного пакета openssh-sftp-server.
(Чтение базы данных … на данный момент установлено 202207 файлов и каталогов.)
Подготовка к распаковке …/openssh-sftp-server_1%3a8.9p1-3ubuntu0.1_amd64.deb …
Распаковывается openssh-sftp-server (1:8.9p1-3ubuntu0.1) …
Выбор ранее не выбранного пакета openssh-server.
Подготовка к распаковке …/openssh-server_1%3a8.9p1-3ubuntu0.1_amd64.deb …
Распаковывается openssh-server (1:8.9p1-3ubuntu0.1) …
Выбор ранее не выбранного пакета ssh.
Подготовка к распаковке …/ssh_1%3a8.9p1-3ubuntu0.1_all.deb …
Распаковывается ssh (1:8.9p1-3ubuntu0.1) …
Выбор ранее не выбранного пакета ncurses-term.
Подготовка к распаковке …/ncurses-term_6.3-2ubuntu0.1_all.deb …
Распаковывается ncurses-term (6.3-2ubuntu0.1) …
Выбор ранее не выбранного пакета ssh-import-id.
Подготовка к распаковке …/ssh-import-id_5.11-0ubuntu1_all.deb …
Распаковывается ssh-import-id (5.11-0ubuntu1) …
Настраивается пакет openssh-sftp-server (1:8.9p1-3ubuntu0.1) …
Настраивается пакет openssh-server (1:8.9p1-3ubuntu0.1) …

Creating config file /etc/ssh/sshd_config with new version
Creating SSH2 RSA key; this may take some time ...
3072 SHA256:U/wQdEXRvJVe38wiZHUarPiSqIshcaB1jBi55DsqxpI root@vlad-VirtualBox (RSA)
Creating SSH2 ECDSA key; this may take some time ...
256 SHA256:umuv53i72k/Xv1vkHU7Ie2suLZBfcFj0SsnVmqTkpNk root@vlad-VirtualBox (ECDSA)
Creating SSH2 ED25519 key; this may take some time ...
256 SHA256:AuOhO82JHCOwHxkaFZ6LB33GVrCIbPl19I9xL0gT0/g root@vlad-VirtualBox (ED25519)
Created symlink /etc/systemd/system/sshd.service → /lib/systemd/system/ssh.service.
Created symlink /etc/systemd/system/multi-user.target.wants/ssh.service → /lib/systemd/system/ssh.service.
rescue-ssh.target is a disabled or a static unit, not starting it.
ssh.socket is a disabled or a static unit, not starting it.
Настраивается пакет ssh-import-id (5.11-0ubuntu1) …
Настраивается пакет ncurses-term (6.3-2ubuntu0.1) …
Настраивается пакет ssh (1:8.9p1-3ubuntu0.1) …
Обрабатываются триггеры для man-db (2.10.2-1) …
Обрабатываются триггеры для ufw (0.36.1-4build1) …
vlad@vlad-VirtualBox:~$ scp vlad user@remote_server:/Users/vlad/filename.txt
ssh: Could not resolve hostname remote_server: Temporary failure in name resolution
lost connection
vlad@vlad-VirtualBox:~$ scp vlad mac@remote_server:/Users/vlad/filename.txt
ssh: Could not resolve hostname remote_server: Temporary failure in name resolution
lost connection
vlad@vlad-VirtualBox:~$ scp vlad vlad@vlad-VirtualBox:/Users/vlad/filename.txt
The authenticity of host 'vlad-virtualbox (127.0.1.1)' can't be established.
ED25519 key fingerprint is SHA256:AuOhO82JHCOwHxkaFZ6LB33GVrCIbPl19I9xL0gT0/g.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'vlad-virtualbox' (ED25519) to the list of known hosts.
vlad@vlad-virtualbox's password: 
vlad: No such file or directory
vlad@vlad-VirtualBox:~$ cat > print100
x=0
while [ $x -lt 102 ]
do
prift "${x} "
let x+=2
done
echo ""
echo "1"            


done


ls -l | cut -c1-c12 | sort |uniq
new111 5
new222 4
new333 3
new222 2
new111 1
done


tree
new1.txt
new2.bak
new3.tmp
new4.backup
 nano newalbom.sh
chmod u+x *
cat newalbom.sh
#!/bin/bash
dir=$1
if [ -e $dir ];then
find $dir -type f \(-name "*.bak" -o -name "*.tmp" -o -name "backup" \) -delete
else         
echo "Error"
fi
./nano newalbom.sh



