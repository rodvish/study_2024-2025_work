---
## Front matter
title: "Отчёт по лабораторной работе 5"
subtitle: "Управление системными службами"
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

Получить навыки управления системными службами операционной системы посред-
ством systemd.

# Выполнение лабораторной работы

Получаем полномочия администратора

![root](image/1.png){ #fig:001 width=70% height=70% }

Проверяем статус службы Very Secure FTP

![Проверка статуса службы](image/2.png){ #fig:002 width=70% height=70% }

Установка службы Very Secure FTP

![Установка](image/3.png){ #fig:003 width=70% height=70% }

Запускаем службу Very Secure FTP

![Пуск](image/4.png){ #fig:004 width=70% height=70% }

Проверяю статус службы Very Secure FTP

![Проверка](image/5.png){ #fig:005 width=70% height=70% }

Добавляю службу Very Secure FTP в автозапуск, проверяю статус, удаляю службу и снова проверяю статус

![Работа со службой](image/6.png){ #fig:005 width=70% height=70% }

Вывожу на экран символические ссылки

![Вывод на экран](image/7.png){ #fig:005 width=70% height=70% }

Снова добавляю службу Very Secure FTP в автозапуск

![Служба Very Secure FTP](image/8.png){ #fig:006 width=70% height=70% }

Проверяю статус службы Very Secure FTP

![Статус Very Secure FTP](image/9.png){ #fig:006 width=70% height=70% }

Вывожу на экран список зависимостей юнита

![Список зависимостей юнита](image/10.png){ #fig:007 width=70% height=70% }

Вывожу на экран список юнитов

![Список юнитов](image/11.png){ #fig:007 width=70% height=70% }

Установка iptables

![Установка](image/12.png){ #fig:007 width=70% height=70% }

Проверяю статус

![Статус](image/13.png){ #fig:008 width=70% height=70% }

Пробую запустить firewalld и iptables

![Запуск](image/24.png){ #fig:009 width=70% height=70% }
 
Ввод команды

![Настройки конфликтов](image/14.png){ #fig:010 width=70% height=70% }

Ввод команды

![Настройки конфликтов](image/25.png){ #fig:010 width=70% height=70% }
 
Выгружаю службу iptables и загружаю службу firewalld

![Выгрузка и загрузка службы](image/15.png){ #fig:011 width=70% height=70% }

Заблокирую запуск iptables

![Блокировка запуска](image/26.jpg){ #fig:012 width=70% height=70% }

Пробую запустить iptables:

![Попытка запуска](image/16.png){ #fig:013 width=70% height=70% }
 
Пробую добавить iptables в автозапуск

![Попытка добавить iptables в автозапуск](image/17.png){ #fig:014 width=70% height=70% }

Перехожу в каталог systemd и нахожу список всех целей, которые можно изолировать

![Поиск необходимых целей](image/18.png){ #fig:015 width=70% height=70% }

Переключаю операционную систему в режим восстановления

![Режим восстановления](image/19.jpg){ #fig:015 width=70% height=70% }

Перезапускаю ОС

![Перезапуск ОС](image/20.jpg){ #fig:015 width=70% height=70% }

Вывожу на экран цель, установленную по умолчанию

![Цель](image/21.png){ #fig:015 width=70% height=70% }

Запускаю текстовый режим

![Запуск текстового режима](image/22.jpg){ #fig:016 width=70% height=70% }

Запускаю графический режим

![Запуск графического режима](image/23.jpg){ #fig:015 width=70% height=70% }

# Вывод

Мы получили навыки управления системными службами операционной системы посред-
ством systemd.

# Контрольные вопросы

1. Что такое юнит (unit)? Приведите примеры.
О: Юнит — это базовый объект systemd (сервис, сокет, устройство, точка монтирования и т.д.). 
Примеры: `nginx.service`, `sshd.socket`, `home.mount`.

2. Какая команда позволяет убедиться, что цель больше не входит в список автоматического запуска при загрузке системы?
О: `systemctl disable <цель>`.

3. Какую команду вы должны использовать для отображения всех сервисных юнитов, которые в настоящее время загружены?
О: `systemctl list-units --type=service`.

4. Как создать потребность (wants) в сервисе?*
О: Создать символическую ссылку в `/etc/systemd/system/<цель>.wants/`: 
`systemctl add-wants <цель> <сервис>`.

5. Как переключить текущее состояние на цель восстановления (rescue target)?
О:`systemctl rescue`.

6. Поясните причину получения сообщения о том, что цель не может быть изолирована.
О: Обычно это происходит, если у цели нет собственного процесса (например, `default.target`), или отсутствуют зависимости для изоляции.

7. Вы хотите отключить службу systemd, но, прежде чем сделать это, вы хотите узнать, какие другие юниты зависят от этой службы. Какую команду вы бы использовали?
О: `systemctl list-dependencies <сервис>`.
