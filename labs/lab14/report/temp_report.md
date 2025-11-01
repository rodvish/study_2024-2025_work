---
## Front matter
title: "Отчёт по лабораторной работе 8"
subtitle: "Планировщики событий"
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

Получение навыков работы с планировщиками событий cron и at.

# Выполнение лабораторной работы

Получаем полномочия администратора

![root](image/1.png){ #fig:001 width=70% height=70% }

Посмотрели статус демона crond

![Статус crond](image/2.png){ #fig:002 width=70% height=70% }

Посмотрели содержимое файла конфигурации /etc/crontab

![Файл конфигурации](image/3.png){ #fig:003 width=70% height=70% }

Посмотрели список заданий в расписании

![Список заданий](image/4.png){ #fig:004 width=70% height=70% }

Открыли файл расписания и добавили предоставленную строку

![Файл расписания](image/5.png){ #fig:005 width=70% height=70% }

Посмотрели список заданий в расписании

![Список заданий](image/6.png){ #fig:005 width=70% height=70% }

Просмотрели журнал системных событий

![Журнал системных событий](image/7.png){ #fig:005 width=70% height=70% }

Изменили запись в расписании crontab

![Запись в crontab](image/8.png){ #fig:006 width=70% height=70% }

Посмотрели список заданий в расписании

![Список заданий](image/9.png){ #fig:006 width=70% height=70% }

Перешли в каталог /etc/cron.hourly и создали в нём файл сценария с именем eachhour

![Создание файла сценария](image/10.png){ #fig:007 width=70% height=70% }

Открыли файл eachhour для редактирования и прописали в нём предоставленный скрипт

![Файл eachhour](image/11.png){ #fig:007 width=70% height=70% }

Сделали файл сценария eachhour исполняемым

![Файл eachhour](image/12.png){ #fig:007 width=70% height=70% }

Перешли в каталог /etc/crond.d и создали в нём файл с расписанием eachhour

![Файл eachhour](image/13.png){ #fig:008 width=70% height=70% }

Просмотрели журнал системных событий

![Журнал системных событий](image/14.png){ #fig:009 width=70% height=70% }
 
Получаем полномочия администратора

![root](image/1.png){ #fig:001 width=70% height=70% }

Проверили, что служба atd загружена и включена

![Служба atd](image/15.png){ #fig:009 width=70% height=70% }

Задали выполнение команды logger message from at в 14:21

![logger message from at](image/16.png){ #fig:009 width=70% height=70% }

Убедились, что задание действительно запланировано

![Запланированное задание](image/17.png){ #fig:009 width=70% height=70% }

# Вывод

Мы получили навыки работы с планировщиками событий cron и at

# Контрольные вопросы

1. Как настроить задание cron, чтобы оно выполнялось раз в 2 недели?

Ответ: Можно использовать два подхода:
- `0 0 */14 * *` - выполнение каждые 14 дней
- `0 0 1,15 * *` - выполнение 1-го и 15-го числа каждого месяца (что примерно соответствует 2 неделям)

2. Как настроить задание cron, чтобы оно выполнялось 1-го и 15-го числа каждого месяца в 2 часа ночи?

Ответ: `0 2 1,15 * *`

3. Как настроить задание cron, чтобы оно выполнялось каждые 2 минуты каждый день?

Ответ: `*/2 * * * *`

4. Как настроить задание cron, чтобы оно выполнялось 19 сентября ежегодно?

Ответ: `0 0 19 9 *`

5. Как настроить задание cron, чтобы оно выполнялось каждый четверг сентября ежегодно?

Ответ: `0 0 * 9 4`

6. Какая команда позволяет вам назначить задание cron для пользователя alice? Приведите подтверждающий пример.

Ответ: Команда `crontab -e -u alice` или редактирование системного файла через `sudo crontab -e -u alice`

Пример:
sudo crontab -e -u alice

И добавление строки: `0 14 * * * /home/alice/backup.sh`

7. Как указать, что пользователю bob никогда не разрешено назначать задания через cron? Приведите подтверждающий пример.

Ответ: Добавить пользователя bob в файл `/etc/cron.deny`

Пример:
echo "bob" | sudo tee -a /etc/cron.deny

8. Вам нужно убедиться, что задание выполняется каждый день, даже если сервер во время выполнения временно недоступен. Как это сделать?

Ответ: Использовать anacron вместо cron, так как anacron предназначен для выполнения пропущенных заданий при простое системы. Альтернативно можно настроить cron в сочетании с механизмом повторных попыток или использовать систему инициализации, которая перезапускает cron-сервис.

9. Какая команда позволяет узнать, запланированы ли какие-либо задания на выполнение планировщиком atd?

Ответ: Команда `atq` (показывает очередь заданий at)
