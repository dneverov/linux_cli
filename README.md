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
