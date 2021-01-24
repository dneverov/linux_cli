# linux_cli

...

## Chapter 3

### `file`

Команда `file` выводит краткое описание содержимого файла.

```
file file_name
file README.md
```

### `less`

Команда `less` — это программа для просмотра содержимого текстовых файлов.

```
less README.md
less /etc/passwd
```

...  
`h` — вывод экрана со справкой  
`q` — quit


### Каталоги в системе Linux

> Используйте `cd`, `ls -l`, `less`

`/` — Корневой каталог

`/bin` — Содержит двоичные файлы, необходимые для загрузки и функционирования системы

`/boot` — Содержит ядро Linux, образ начального RAM-диска (с драйверами, необходимыми на этапе загрузки) и сам загрузчик.  
Интересные файлы:
- `/boot/grub/grub.conf` или `menu.lst`, используются для настройки загрузчика.  
- `/boot/vmlinuz` (или с похожим именем), ядро Linux

`/dev` — Специальный каталог, содержащий _узлы устройств._

`/etc` — Содержит все системные конфигурационные файлы.  
Интересные файлы:
- `/etc/crontab` — файл, определящий время запуска автоматизированных заданий;
- `/etc/fstab` — таблица устройств хранения и соответствующих им точек монтирования;
- `/etc/passwd` — список всех учетных записей пользователей.

`/home` — каталоги пользователей

`/lib` — Содержит файлы разделяемых библиотек, используемых основными системными программами

`/lost+found` — Каждый раздел или устройство, отформатированные с использованием файловой системы Linux, такой как ext3, будут иметь этот каталог. Он используется на случай частичного восстановления повреждений в файловой системе. Если с системой ничего страшного не происходило, этот каталог будет оставаться пустым.

`/media` — В современных системах Linux каталог _/media_ будет содержать точки монтирования съёмных носителей, таких как USB-диски, CD-ROM и т.д., которые монтируются в момент подключения

`/mnt` — В старых системах Linux каталог _/mnt_ содержал точки монтирования съёмных носителей, монтируемых вручную

`/opt` — Каталог _/opt_ используется для установки «необязательного» (optional) программного обеспечения, в основном для установки коммерческого ПО

`/proc` — Специальный каталог. Не явяется фактической файловой системой, в том смысле, что файлы в этом каталоге не хранятся на жестком диске. Это виртуальная файловая система, поддерживаемая ядром Linux. Файлы в ней являются «глазками», через которые можно заглянуть в ядро. Эти файлы доступны для чтения и помогают «увидеть» компьютер глазами ядра

`/root` — Домашний каталог пользователя root

`/sbin` — Каталог содержит системные двоичные файлы (system binaries). Эти прграммывыполняют жизненно важные задачи и обыно запускаются только суперпользователем

`/tmp` — Каталог `/tmp` играет роль временного хранилища для временных файлов, создаваемых разными программами. В некоторых конфигурациях этот каталог принудительно очищается при перезапуске системы

`/usr` — Дерево каталогов `/usr` является, пожалуй, самым обЪъемным в системе Linux. В нем хранятся все программы и файлы поддержки, используемые обычными пользователями

- `/usr/bin` — Каталог `/usr/bin` содержит выполняемые программы, установленные дистрибутивом Linux. Очень часто в этом каталоге хранятся тысячи программ

- `/usr/lib` — Содержит разделяемые библиотеки для программ в `/usr/bin`

- `/usr/local` — Дерево каталогов `/usr/local` используется для установки тех программ, которые не входят в состав дистрибутива, но должны быть доступны всем пользователям в системе. Программы, собираемые из исходных текстов, обычно устанавливаются в `/usr/local/bin`. В новейших версиях системы Linux это дерево каталогов присутствует, но остается пустым, пока системный администратор не добавит туда что-нибудь

- `/usr/sbin` — Содержит дополнительные программы для администрирования

- `/usr/share` — Каталог `/usr/share` содержит все разделяемые данные, используемые пррограммами в `/usr/bin`, в том числе конфигурационные файлы с настройками по умолчанию, ярлыки, фоновые изображения для рабочего стола, звуковые файлы и т. д.

  - `/usr/share/doc` — Большинство пакетов, установленных в системе, содержат документацию. Вся эта документация, организованная по пакетам, хранится в этом каталоге

`/var` — За исключением `/tmp` и `/home`, все упоминавшиеся выше каталоги остаются относительно статичными; то есть их содержимое почти не меняется. Дерево каталогов `/var` — как раз то место, где хранятся часто изменяемые данные: различные базы данных, буферные файлы, почта пользователей и пр.

- `/var/log` — Каталог `/var/log` содержит файлы журналов с записями о различных действиях, выполнявшихся в системе. Они очень важны и должны проверяться время от времени. Наиболее полезными являются файлы `/var/log/messages` и `/var/log/syslog`. Обратите внимание, что из соображений безопасности некоторые системы требуют привилегий суперпользователя для просмотра файлов журналов.


### Символические ссылки

```
lrwxrwxrwx 1 root root        6 авг 16 03:31 animate -> magick
```

Обратили внимание на первую букву `l` и на присутствие двух имен файлов в конце? Это специальный файл, который называется _символической ссылкой_, _мягкой ссылкой_ или _симлинком_.


### Жесткие ссылки

...Существует второй тип ссылок, который называют _жесткими ссылками_ (hard link). Они также позволяют присвоить одному файлу несколько имен, но они действуют иначе. Подробнее о различиях между жесткими и символическими ссылками — в след. главе.

[Глава 4](ch04/index.md)
