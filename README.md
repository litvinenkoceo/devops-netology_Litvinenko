# 5. Ресурсы выделенные по умолчанию
- 2 CPU with Acceleration
- RAM 1024 mb
- Video RAM 64m
- HDD SATA AHCI Virtual size 64 Gb (1,73 Gb Real size)
- Network mode NAT

# 6 Добавить оперативной памяти или ресурсов процессора виртуальной машине
В теле скрипта, например:
> v.memory = 2048

> v.cpus = 4

# 8 Настройки истории Bash
setting in Ubuntu 20.04     (строчка 1178 в man bash)
> echo $HISTSIZE

>1000

>echo $HISTFILESIZE

>2000

### Смена настроек происходит либо bashrc юзера или глобальная.
> vim ~/.bashrc

### ignoreboth 
Директива игнорирует попадания дубликатов одновременно с строками с пробелами, является суммой двух команд:
> ignoreboth=ignoredups + ignorespace

# 9 { } Сценарии использования - групповая операция. 
описаны   man bash 262 строка,
 { list; }
list  is  simply executed in the current shell environment.  list must be terminated with a newline
or semicolon.  This is known as a group command.

# 10 однократным вызовом Touch 10000
> touch {1..10000}
-------------------
> touch {1..300000}

> bash: /usr/bin/touch: Argument list too long

# 11 [[ ]]
Начиная с версии 2.02, Bash предоставляет в распоряжение программиста конструкцию [[ ... ]] расширенный вариант команды test, которая выполняет сравнение способом более знакомым программистам, пишущим на других языках программирования
## Проверка наличия папки
> [[ -d /tmp ]]

# 12 Путь + type -a bash
> mkdir /tmp/new_path

> ln -s /bin/bash /tmp/new_path

> export PATH=/tmp/new_path:$PATH

> type -a bash


# 13 Разница между batch и at
- at выполняет задачи в назначенное время.
- batch выполняет задачи во время периодов низкой загруженности системы; другими словами, когда средний уровень загрузки системы падает ниже значения 1.5 или того значения, которое задано при вызове atd.
 
