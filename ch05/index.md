# 5. Работа с командами

В этой главе будут представлены следующие команды:

- **`type`** — сообщает, как интерпретируется имя указанной команды;
- **`which`** — сообщает, какая программа будет выполнена;
- **`help`** — выводит справку по встроенным командам оболочки;
- **`man`** — выводит страницу справочного руководства с описанием команды;
- **`apropos`** — выводит список подходящих команд;
- **`info`** — выводит запись из справочного руководства _Info_ с описанием команды;
- **`whatis`** — выводит краткое описание команды;
- **`alias`** — создает псавдоним для команды;


## Что такое команды?

Команда может быть:

- **Выполняемой программой** — _скомпилированные двоичные программы_, _программы на языках сценариев_;
- **Встроенной командой** — _shell builtins_ (E.g. `cd`);
- **Функцией командной оболочки** — _shell functions_, — миниатюрные сценарии на языке командной оболочки, встроенные в _окружение_;
- **Псевдоним** — _alias_, — это команда, которую мы можем определить сами, сконструировав из других команд;


## Идентификация команд

### `type` — получение типа команды

Команда **`type`** — это встроенная команда, которая сообщает тип указанной ей команды

```
type команда
```

```
$ type type
type is a shell builtin

$ type ls
ls is aliased to `ls --color=auto'

$ type cp
cp is /bin/cp
```


### `which` — определение местоположения выполняемого файла

```
$ which ls
/bin/ls
```

**`which`** ищет только исполняемые программы, она не способна выявлять встроенные команды или псевдонимы.



### `help` — получение справки для встроенных команд

```
$ help cd
cd: cd [-L|[-P [-e]] [-@]] [dir]
    Change the shell working directory.
    
    Change the current directory to DIR.  The default DIR is the value of the
    HOME shell variable.
...
```

Квадратные скобки указывают на необязательность элемента. Вертикальная черта используется для перечисления взаимоисключающих вариантов.


### `--help` — вывод инструкции по использованию

```
$ mkdir --help
Usage: mkdir [OPTION]... DIRECTORY...
Create the DIRECTORY(ies), if they do not already exist.
...

```


### `man` — вывод страниц справочного руководства

```
man программа
```

```
man ls
```

#### 5.1 Организация справочного руководства

**Раздел / Содержит**

1. Пользовательские команды
2. Программные интерфейсы системных вызовов в ядре
3. Программные интерфейсы в библиотеке С
4. Специальные файлы, такие как узлы устройств и драйверы
5. Форматы файлов
6. Игры и развлечения, такие как хранители экрана
7. Прочее
8. Команды системного администрирования


```
man раздел искомый_термин
```

```
man 5 passwd
```

выведет страницу с описанием формата файла _`/etc/passwd`_


### `apropos` — вывод списка подходящих команд

```
$ apropos partition
addpart (8)          - tell the kernel about the existence of a partition
cfdisk (8)           - display or manipulate a disk partition table
cgdisk (8)           - Curses-based GUID partition table (GPT) manipulator
delpart (8)          - tell the kernel to forget about a partition
fdisk (8)            - manipulate disk partition table
fixparts (8)         - MBR partition table repair utility
gdisk (8)            - Interactive GUID partition table (GPT) manipulator
iostat (1)           - Report Central Processing Unit (CPU) statistics and in...
mpartition (1)       - partition an MSDOS hard disk
partprobe (8)        - inform the OS of partition table changes
partx (8)            - tell the kernel about the presence and numbering of on...
resizepart (8)       - tell the kernel about the new size of a partition
sfdisk (8)           - display or manipulate a disk partition table
sgdisk (8)           - Command-line GUID partition table (GPT) manipulator fo...
systemd-gpt-auto-generator (8) - Generator for automatically discovering and ...
```

Первое поле — имя страницы, второе поле — номер раздела.


### `whatis` — вывод очень краткого описания команды

```
$ whatis ls
ls (1)               - list directory contents
```


### `info` — вывод записи из справочного руководства _Info_

```
$ info ls
```

```
$ info coreutils
```

#### 5.2 Команды программы _Info_

