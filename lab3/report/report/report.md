---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №3"
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

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.

# Задание

Выпонить порядок выполнения лабораторной работы и заполнить таблицы.

# Выполнение лабораторной работы

1. В установленной при выполнении предыдущей лабораторной работы операционной системе создала учётную запись пользователя guest (использую учётную запись администратора).

2. Задала пароль для пользователя guest (использую учётную запись администратора) (рис. -@fig:001).

![Создание пользователя guest](image/1.png){ #fig:001 width=75% }

3. Аналогично создала второго пользователя guest2 (рис. -@fig:002). 

![Создание пользователя guest2](image/2.png){ #fig:002 width=75% }

4. Добавила пользователя guest2 в группу guest (рис. -@fig:003). 

5. Осуществила вход в систему от двух пользователей на двух разных консолях: guest на первой консоли и guest2 на второй консоли.

![Вход в систему от двух пользователей на двух разных консолях](image/3.png){ #fig:003 width=75% }

6. Для обоих пользователей командой pwd определила директорию, в которой я нахожусь (рис. -@fig:004).

![Данные guest](image/4.png){ #fig:004 width=75% }

7. Уточнила имя нашего пользователя, его группу, кто входит в неё и к каким группам принадлежит он сам. Определила командами groups guest и groups guest2, в какие группы входят пользователи guest и guest2 (рис. -@fig:005).

![Данные пользователя](image/5.png){ #fig:005 width=75% }

8. Сравнила полученную информацию с содержимым файла /etc/group (рис. -@fig:006).

![Файл /etc/passwd](image/6.png){ #fig:006 width=75% }

9. От имени пользователя guest2 выполнила регистрацию пользователя guest2 в группе guest (рис. -@fig:007).

![Регистрация пользователя guest2 в группе guest](image/7.png){ #fig:007 width=75% }

10. От имени пользователя guest изменила права директории /home/guest, разрешив все действия для пользователей группы (рис. -@fig:008).

![Изменение прав директории /home/guest](image/8.png){ #fig:008 width=75% }

11. От имени пользователя guest сняла с директории /home/guest/dir1 (рис. -@fig:009).

![Снятие с директории /home/guest/dir1](image/9.png){ #fig:009 width=75% }

12. Заполнила таблицу «Установленные права и разрешённые действия для групп».

![Таблица 2.2.1 Установленные права и разрешенные действия для групп (000), (010)](image/10.png){ #fig:010 width=75% }

![Таблица 2.2.2 Установленные права и разрешенные действия для группы (020)](image/11.png){ #fig:011 width=75% }

![Таблица 2.2.3 Установленные права и разрешенные действия для группы (030)](image/12.png){ #fig:012 width=75% }

![Таблица 2.2.4 Установленные права и разрешенные действия для группы (040)](image/13.png){ #fig:013 width=75% }

![Таблица 2.2.5 Установленные права и разрешенные действия для группы (050)](image/14.png){ #fig:014 width=75% }

![Таблица 2.2.6 Установленные права и разрешенные действия для группы (060)](image/15.png){ #fig:015 width=75% }

![Таблица 2.2.7 Установленные права и разрешенные действия для группы (070)](image/16.png){ #fig:016 width=75% }

13. На основании заполненной таблицы определила те или иные минимально необходимые права для выполнения операций внутри директории dir1, заполнила табл. 3.2.

![Таблица 2.2 Минимальные права для совершения операций от имени пользователей входящих в группу](image/17.png){ #fig:017 width=75% }

# Выводы
После выполнения лабораторной работы №3 я полученла практические навыки работы в консоли с атрибутами файлов для групп пользователей.

