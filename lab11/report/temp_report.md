---
## Front matter
title: "Отчёт по лабораторной работе 11"
subtitle: "Управление загрузкой системы"
author: "Вишняков Родион Сергеевич"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography

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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
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

# Цель работы

Получить навыки работы с загрузчиком системы GRUB2.

# Выполнение лабораторной работы

Получаем полномочия администратора

![root](image/1.png){ #fig:001 width=70% height=70% }

В файле /etc/default/grub установили параметр отображения меню загрузки в течение 10 секунд

![Параметр отобрадения меню загрузки](image/2.png){ #fig:002 width=70% height=70% }

Записали изменения в GRUB2, введя в командной строке

![GRUB2](image/3.png){ #fig:003 width=70% height=70% }

Просмотрели список всех файлов модулей, которые загружены в настоящее время

![Список файлов модулей](image/4.png){ #fig:004 width=70% height=70% }

Просмотрели задействованные переменные среды оболочки

![Среда оболочки](image/5.png){ #fig:005 width=70% height=70% }

Просмотрели список всех загруженных файлов модулей

![Список файлов модулей](image/6.png){ #fig:005 width=70% height=70% }

Перезагрузили систему

![Перезагрузка](image/7.png){ #fig:005 width=70% height=70% }

# Вывод

Мы получили навыки работы с загрузчиком системы GRUB2.

# Контрольные вопросы

1. Какой файл конфигурации следует изменить для применения общих изменений в GRUB2?

Ответ: Для применения общих изменений в GRUB2 следует изменить файл etc/default/grub. Этот файл содержит основные настройки загрузчика, такие как таймаут меню, параметры ядра и другие общие параметры.

2. Как называется конфигурационный файл GRUB2, в котором вы применяете изменения для GRUB2?

Ответ: Основной конфигурационный файл GRUB2, в который применяются изменения, называется boot/grub2/grub.cfg. Однако этот файл генерируется автоматически, и его прямое редактирование не рекомендуется.

3. После внесения изменений в конфигурацию GRUB2, какую команду вы должны выполнить, чтобы изменения сохранились и воспринялись при загрузке системы?

Ответ: После внесения изменений необходимо выполнить команду grub2-mkconfig с параметром -o и указанием пути к файлу grub.cfg, которая перегенерирует основной конфигурационный файл на основе измененных настроек. Это обеспечивает применение всех изменений при следующей загрузке системы.
