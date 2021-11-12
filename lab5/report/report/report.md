---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №5"
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

Изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

# Выполнение лабораторной работы

5.3.1. Создание программы

1. Вошли в систему от имени пользователя guest.

2. Создали программу simpleid.c (рис. -@fig:001).

![Программа simpleid.c](image/1.png){ #fig:001 width=75% }

3. Скомплилировали программу и убедились, что файл программы создан (рис. -@fig:002).

![Компиляция программы](image/2.png){ #fig:002 width=75% }

4. Выполнили программу simpleid (рис. -@fig:003).

![Выполнение программы simpleid](image/3.png){ #fig:003 width=75% }

5. Выполнили системную программу id (рис. -@fig:004). 

![Программа id](image/4.png){ #fig:004 width=75% }

6. Усложнили программу, добавив вывод действительных идентификаторов (рис. -@fig:005). Получившуюся программу назвали simpleid2.c.

![Усложнение программы](image/5.png){ #fig:005 width=75% }

7. Скомпилировали и запустили simpleid2.c (рис. -@fig:006).

![Программа simpleid2.c](image/6.png){ #fig:006 width=75% }

8. От имени суперпользователя выполнили команды (рис. -@fig:007).

![Изменение прав программы](image/7.png){ #fig:007 width=75% }

9. Повысили временно свои права с помощью su.

10. Выполнили проверку правильности установки новых атрибутов и смены владельца файла simpleid2 (рис. -@fig:008).

![Проверка](image/8.png){ #fig:008 width=75% }

11. Запустили simpleid2 и id (рис. -@fig:009).

![Запуск simpleid2 и id](image/9.png){ #fig:009 width=75% }

12. Проделали тоже самое относительно SetGID-бита (рис. -@fig:010).

![SetGID-бита](image/10.png){ #fig:010 width=75% }

13. Создайли программу readfile.c (рис. -@fig:011).

![Программа readfile.c](image/11.png){ #fig:011 width=75% }

14. Откомпилировали её (рис. -@fig:012).

![Компиляция readfile.c](image/12.png){ #fig:012 width=75% }

15. Сменили владельца у файла readfile.c и изменили права так, чтобы только суперпользователь (root) мог прочитать его, a guest не мог (рис. -@fig:013).

![Права файла readfile.c](image/13.png){ #fig:013 width=75% }

16. Проверили, что пользователь guest не может прочитать файл readfile.c (рис. -@fig:014).

![guest не может прочитать файл readfile.c](image/14.png){ #fig:014 width=75% }

17. Сменили у программы readfile владельца и установили SetUID-бит (рис. -@fig:015).

![Права файла readfile.c](image/15.png){ #fig:015 width=75% }

18. Проверили, может ли программа readfile прочитать файл readfile.c (рис. -@fig:016). 

![Права файла readfile.c](image/16.png){ #fig:016 width=75% }

19. Проверили, может ли программа readfile прочитать файл /etc/shadow (рис. -@fig:017).

![Права файла readfile.c](image/17.png){ #fig:017 width=75% }


5.3.2. Исследование Sticky-бита

1. Выяснили, установлен ли атрибут Sticky на директории /tmp (рис. -@fig:018). Да, установлен.

2. От имени пользователя guest создали файл file01.txt в директории /tmp со словом test (рис. -@fig:018).

![Атрибут Sticky и создание file01.txt](image/18.png){ #fig:018 width=75% }

3. Просмотрели атрибуты у только что созданного файла и разрешили чтение и запись для категории пользователей «все остальные» (рис. -@fig:019).

![Атрибуты file01.txt](image/19.png){ #fig:019 width=75% }

4. От пользователя guest2 (не являющегося владельцем) попробовали прочитать файл /tmp/file01.txt (рис. -@fig:020). Получилось.

5. От пользователя guest2 попробовали дозаписать в файл /tmp/file01.txt слово test2 (рис. -@fig:020). Получилось.

6. Проверили содержимое файла (рис. -@fig:020). Получилось.

7. От пользователя guest2 попробовали записать в файл /tmp/file01.txt слово test3, стерев при этом всю имеющуюся в файле информацию (рис. -@fig:020). Получилось.

8. Проверили содержимое файла (рис. -@fig:020). Получилось.

9. От пользователя guest2 попробовали удалить файл /tmp/file01.txt (рис. -@fig:020). Не получилось.

![Проверка](image/20.png){ #fig:020 width=75% }

10. Повысили свои права до суперпользователя и выполнили после этого команду, снимающую атрибут t (Sticky-бит) с директории /tmp (рис. -@fig:021).

11. Покинули режим суперпользователя (рис. -@fig:021).

12. От пользователя guest2 проверили, что атрибута t у директории /tmp нет (рис. -@fig:021).

13. Повторили предыдущие шаги (рис. -@fig:021).

14. Удалось удалить файл от имени пользователя, не являющегося его владельцемт (рис. -@fig:021).

![Проверка](image/21.png){ #fig:021 width=75% }

15. Повысили свои права до суперпользователя и вернули атрибут t на директорию /tmp (рис. -@fig:022).

![Возвращаем атрибут t](image/22.png){ #fig:022 width=75% }

# Выводы
После выполнения лабораторной работы №5 мы изучили механизмы изменения идентификаторов, применения SetUID- и Sticky-битов. Получили практические навыки работы в консоли с дополнительными атрибутами. Рассмотрели работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.

