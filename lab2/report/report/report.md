---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №2"
subtitle: "Дисциплина: Информационная безопасность"
author: "Шапошникова Айталина Степановна, НПИбд-02-18"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Получение практических навыков работы в консоли с атрибутами файлов, закрепление теортитических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе OC Linux.

# Задание

Выпонить порядок выполнения лабораторной работы и заполнить таблицы.

# Выполнение лабораторной работы

1. В установленной при выполнении предыдущей лабораторной работы операционной системе создала 
учётную запись пользователя guest (использую учётную запись администратора).

2. Задала пароль для пользователя guest (использую учётную запись администратора) (рис. -@fig:001).

![Создание пользователя guest](image/1.png){ #fig:001 width=75% }

3. Вошла в систему от имени пользователя guest (рис. -@fig:002). 

![Вход в систему](image/2.png){ #fig:002 width=75% }

4. Определила директорию, в которой нахожусь, командой pwd. Она не отличается с приглашением 
командной строки. Она является моей домашней директорией. 

5. Уточнила имя пользователя командой whoami.

6. Уточнила имя пользователя, группу, а также группы, куда входит пользователь, командой id. 
Выведенные значения uid, gid и др. запомнила. У нас одна группа (рис. -@fig:003).

![Данные guest](image/3.png){ #fig:003 width=75% }

7. Полученную информацию об имени пользователя совпадает с данными, выводимыми в приглашении командной строки.

8. Просмотрела файл /etc/passwd  используя программу grep в качестве фильтра для вывода только 
строк, содержащих определённые буквенные сочетания (рис. -@fig:004). Определила uid=1001, gid=1001.  Они совпадают с тем, что у нас вышло в предыдущих пунктах.

![Файл /etc/passwd](image/6.png){ #fig:004 width=75% }

9. Определила существующие в системе директории (рис. -@fig:005). Получила список поддиректорий 
директории /home. На всех стоит права drwx------, право читать, писать, запускать только у владельца директории.

![Директории](image/7.png){ #fig:005 width=75% }

10. Проверила, какие расширенные атрибуты установлены на поддиректориях, находящихся в директории /home (рис. -@fig:006). Удалось увидеть расширенные атрибуты директории только пользователя guest.

![Расширенные атрибуты директории /home](image/8.png){ #fig:006 width=75% }

11. Создала в домашней директории поддиректорию dir1 (рис. -@fig:007). Определила командой ls -l 
права доступа и расширенные атрибуты были выставлены на директорию dir1. Разрешено владельцу и группе чтение, запись и запуск, а другим пользователям только выполнение (запуск).

![Поддиректория dir1](image/9.png){ #fig:007 width=75% }

12. Сняла с директории dir1 все атрибуты (рис. -@fig:008).

![Поддиректория dir1 без атрибутов](image/10.png){ #fig:008 width=75% }

13. Попыталась создать в директории dir1 файл file1, не получилось, так как у нас нет прав создавать файлы. У нас нет прав промотра файлов директории. Файла там нет так как он не создался (рис. -@fig:009).

![File1](image/11.png){ #fig:009 width=75% }

14. Заполнила таблицу «Установленные права и разрешённые действия».

![Таблица 2.2.1 Установленные права и разрешенные действия (000), (100)](image/12.png){ #fig:010 width=75% }

![Таблица 2.2.2 Установленные права и разрешенные действия (200)](image/13.png){ #fig:011 width=75% }

![Таблица 2.2.3 Установленные права и разрешенные действия (300)](image/14.png){ #fig:012 width=75% }

![Таблица 2.2.4 Установленные права и разрешенные действия (400)](image/15.png){ #fig:013 width=75% }

![Таблица 2.2.5 Установленные права и разрешенные действия (500)](image/16.png){ #fig:014 width=75% }

![Таблица 2.2.6 Установленные права и разрешенные действия (600)](image/17.png){ #fig:015 width=75% }

![Таблица 2.2.7 Установленные права и разрешенные действия (700)](image/18.png){ #fig:016 width=75% }

15. На основании заполненной таблицы определила те или иные минимально необходимые права для выполнения операций внутри директории dir1, заполнила табл. 2.2.

![Таблица 2.2 Минимальные права для совершения операций](image/19.png){ #fig:017 width=75% }

# Выводы
После выполнения лабораторной работы №2 я получила практические навыки работы в консоли с атрибутами файлов, закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.

