---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №4"
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

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

# Задание

Опробовать действие на практике расширенных атрибутов «а» и «i».

# Выполнение лабораторной работы

1. От имени пользователя guest определили расширенные атрибуты файла /home/guest/dir1/file1 (рис. -@fig:001).

![Определение расширенных атрибутов файла /home/guest/dir1/file1](image/1.png){ #fig:001 width=75% }

2. Установили командой chmod 600 file1 на файл file1 права, разрешающие чтение и запись для владельца файла (рис. -@fig:002).

![Установка прав на файл file1](image/2.png){ #fig:002 width=75% }

3. Попробовали установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest. В ответ мы получили отказ от выполнения операции.(рис. -@fig:003).

![Расширенный атрибут a](image/3.png){ #fig:003 width=75% }

4. Зашли на третью консоль с правами администратора либо повысили свои права с помощью команды su. Установили расширенный атрибут a на файл /home/guest/dir1/file1 от имени суперпользователя (рис. -@fig:004). 

![Расширенный атрибут a](image/4.png){ #fig:004 width=75% }

5. От пользователя guest проверили правильность установления атрибута (рис. -@fig:005).

![Чтение файла file1](image/5.png){ #fig:005 width=75% }

6. Выполнили дозапись в файл file1 слова «test». После этого выполнили чтение файла file1. Убедились, что слово test было успешно записано в file1 (рис. -@fig:006).

![Дозапись в файл file1](image/6.png){ #fig:006 width=75% }

7. Попробовали удалить файл file1 либо стереть имеющуюся в нём информацию. Попробовали переименовать файл. Не получилось (рис. -@fig:007).

![Удаление файла и переименование файла](image/7.png){ #fig:007 width=75% }

8. Попробовали установить на файл file1 права, например, запрещающие чтение и запись для владельца файла. Тоже не получилось (рис. -@fig:008).

![Установка прав на файл file1](image/8.png){ #fig:008 width=75% }

9. Сняли расширенный атрибут a с файла /home/guest/dirl/file1 от имени суперпользователя (рис. -@fig:009). Повторили операции, которые нам ранее не удавалось выполнить (стереть имеющуюся в файле информацию, переименовать файл, установить права доступа). Все получилось (рис. -@fig:010).

![Снятие расширенного атрибута a](image/9.png){ #fig:009 width=75% }

![Повтор неполучившихся операций](image/10.png){ #fig:010 width=75% }

10. Повторили наши действия по шагам, заменив атрибут «a» атрибутом «i» (рис. -@fig:011). Нам не удалось дозаписать информацию в файл, а также стереть имеющуюся в файле информацию, переименовать файл, установить права доступа (рис. -@fig:012).

![Расширенный атрибут i](image/11.png){ #fig:011 width=75% }

![Выполнение операций](image/12.png){ #fig:012 width=75% }

# Выводы
После выполнения лабораторной работы №4 мы повысили свои навыки использования интерфейса командой строки (CLI), познакомились на примерах с тем, как используются основные и расширенные атрибуты при разграничении доступа. Имели возможность связать теорию дискреционного разделения доступа (дискреционная политика безопасности) с её реализацией на практике в ОС Linux. Составили наглядные таблицы, поясняющие какие операции возможны при тех или иных установленных правах. Опробовали действие на практике расширенных атрибутов «а» и «i».

