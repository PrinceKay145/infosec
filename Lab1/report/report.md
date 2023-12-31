---
## Front matter
title: "Отчёта по лабораторной работе № 1"
subtitle: "Информационная безопасность"
author: "Адебайо Ридвануллахи Айофе"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

## Цель работы

* Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

* Изучить идеологию и применение средств контроля версий.

* Освоить умения по работе с git.

* Научиться оформлять отчёты с помощью легковесного языка разметки Markdown.

## Задание

Получите следующую информацию.

1. Версия ядра Linux (Linux version).

2. Частота процессора (Detected Mhz processor).

3. Модель процессора (CPU0).

4. Объем доступной оперативной памяти (Memory available).

5. Тип обнаруженного гипервизора (Hypervisor detected).

6. Тип файловой системы корневого раздела.

## Теоретическое введение

Системы контроля версий (Version Control System, VCS) применяются при работе несколь ких человек над одним проектом. Обычно основное дерево проекта хранится в локальном или удалённом репозитории, к которому настроен доступ для участников проекта. При внесении изменений в содержание проекта система контроля версий позволяет их фиксировать, совмещать изменения, произведённые разными участниками проекта,производить откат к любой более ранней версии проекта, если это требуется.

В классических системах контроля версий используется централизованная модель, предполагающая наличие единого репозитория для хранения файлов. Выполнение большинства функций по управлению версиями осуществляется специальным сервером. Участник проекта (пользователь) перед началом работы посредством определённых команд получает нужную ему версию файлов. После внесения изменений, пользователь размещает новую версию в хранилище. При этом предыдущие версии не удаляются из центрального хранилища и к ним можно вернуться в любой момент. Сервер может сохранять не полную версию изменённых файлов, а производить так называемую дельтакомпрессию — сохранять только изменения между последовательными версиями, что позволяет уменьшить объём хранимых данных.

Системы контроля версий поддерживают возможность отслеживания и разрешения конфликтов, которые могут возникнуть при работе нескольких человек над одним файлом. Можно объединить (слить) изменения, сделанные разными участниками (автоматически или вручную), вручную выбрать нужную версию, отменить изменения вовсе или заблокировать файлы для изменения. В зависимости от настроек блокировка не позволяет другим пользователям получить рабочую копию или препятствует изменению рабочей копии файла средствами файловой системы ОС, обеспечивая таким образом, привилегированный доступ только одному пользователю, работающему с файлом.

Системы контроля версий также могут обеспечивать дополнительные, более гибкие функциональные возможности. Например, они могут поддерживать работу с несколькими версиями одного файла, сохраняя общую историю изменений до точки ветвления версий и собственные истории изменений каждой ветви. Кроме того, обычно доступна информация о том, кто из участников, когда и какие изменения вносил. Обычно такого рода информация хранится в журнале изменений, доступ к которому можно ограничить.

В отличие от классических, в распределённых системах контроля версий центральный репозиторий не является обязательным.

Среди классических VCS наиболее известны CVS, Subversion, а среди распределённых — Git, Bazaar, Mercurial. Принципы их работы схожи, отличаются они в основном синтаксисом используемых в работе команд.

## Выполнение лабораторной работы

**1. Установка операционной системы**

Я установил CentOS 9 на виртуальную машину.

![Virtual Machine CentOS](../5.png){#fig:001 width=50%}

**2. Настройка пользователя**

![Creating user](../1.png){#fig:001 width=50%}

**3. Гостевая ОС**

![Запуск образа диска дополнений гостевой ОС](../4.png){#fig:001 width=50%}

**4. Команда `dmesg`**

![dmesg](../3.png){#fig:001 width=50%}

**5. Команда `dmegs | less`**

![dmesg|less](../2.png){#fig:001 width=50%}

**Домашнее задание**

1. Версия ядра Linux (Linux version): 5.14.0-362.el9.x86_64

2. Частота процессора (Detected Mhz processor):2304.008 Mhz

3. Модель процессора (CPU0): Intel(R) Core(TM) i7-10510U CPU @ 1.80GHz

4. Объем доступной оперативной памяти (Memory available):260860K

5. Тип обнаруженного гипервизора (Hypervisor detected): KVM

![Поиск информации с помощью grep](../7.png){#fig:001 width=50%}

6. Тип файловой системы корневого раздела: XFS

![Поиск информации с помощью grep](../8.png){#fig:001 width=50%}

## Контрольные Вопросы

1. Какую информацию содержит учётная запись пользователя?

Учетная запись пользователя - это необходимая для системы информация о пользователе, которая хранится в специальных файлах. Вся информация о пользователе обычно хранится в файлах /etc/passwd и /etc/group. Учетная запись пользователя содержит: имя пользователя (user name), идентификационный номер группы (GID), идентификационный номер пользователя (UID), пароль (password), полное имя (full name), домашний каталог (home directory), начальную оболочку (login shell).

2. Укажите команды терминала и приведите примеры:

* для получения справки по команде: man команда.
* для перемещения по файловой системе: cd путь.
* для просмотра содержимого каталога: ls опции путь.
* для определения объёма каталога: du опция путь.
* для создания / удаления каталогов / файловв: mkdir опции путь /
rmdir опции путь / rm опции путь.
* для задания определённых прав на файл / каталогг: chmod опции путь.
* для просмотра истории команд: history опции

3. Что такое файловая система? Приведите примеры с краткой характеристикой.

Файловая система имеет два значения: с одной стороны - это архитектура
хранения битов на жёстком диске, с другой - это организация каталогов
в соответствии с идеалогией Linux. Файловая система - это архитектура
хранения данных в системе, хранение данных в оперативной памяти и
доступа к конфигурации ядра. В физическом смысле файловая система
Linux представляет собой пространство раздела диска, разбитое на блоки
фиксированного размера. Их размер кратен размеру сектора: 1024, 2048,
4096 или 8120 байт.

4. Как посмотреть, какие файловые системы подмонтированы в ОС?

Команда “findmnt” или “findmnt –all” будет отображать все подмонтированные файловые системы или искать файловую систему.

5. Как удалить зависший процесс?

Команда “kill -сигнал pid_процесса” позволяет удалить зависший процесс,
где PID - уникальный идентификатор процесса.

## Выводы

приобретил практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов. Изучил идеологию и применение средств контроля версий. Освоил умения по работе с git. Научился оформлять отчёты с помощью легковесного языка разметки Markdown.

## Список литературы

Кулябов Д. С.  *Лабораторная работа №1**: 000-methodical.pdf*

Кулябов Д. С.  *Лабораторная работа №1**: 001-lab_virtualbox.pdf*

Кулябов Д. С.  *Лабораторная работа №1**: 002-lab_vcs.pdf*

Кулябов Д. С.  *Лабораторная работа №1**: 003-lab_markdown.pdf*

СentOS [Электронный ресурс]. Free Software Foundation.
URL: <https://www.centos.org/centos-stream/>
