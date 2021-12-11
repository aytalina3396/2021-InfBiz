---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №7"
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

Освоить на практике применение режима однократного гаммирования.

# Выполнение лабораторной работы

7.3. Порядок выполнения работы

1. Изучили указание к работе. Выяснили как работает однократное гаммирование.

2. Написали функцию для создания рандомного ключа (рис. -@fig:001).

![generate_key](image/1.png){ #fig:001 width=90% }

3. Написали  функцию для перевода слов в шестнадцатеричную систему счисления (рис. -@fig:002).

![convert_hexadecimal_form](image/2.png){ #fig:002 width=90% }

4. Написали  функцию однократного гаммирования (рис. -@fig:003).

![single_gamming](image/3.png){ #fig:003 width=90% }

5. Написали программу, где создали рандомный ключ и перевели в шестнадцатеричную систему счисления. Зашифровали наш открытый текст "С Новым Годом, друзья!" и также перевели в шестнадцатеричную систему счисления (рис. -@fig:004).

![Зашифровка текста](image/4.png){ #fig:004 width=90% }

6. Написали программу, где создали рандомный ключ и перевели в шестнадцатеричную систему счисления. Расщифровали наш текст, полученный в предыдущем пункте (рис. -@fig:005).

![Расшифровка текста](image/5.png){ #fig:005 width=90% }

# Выводы
После выполнения лабораторной работы №7 мы освоили на практике применение режима однократного гаммирования.

