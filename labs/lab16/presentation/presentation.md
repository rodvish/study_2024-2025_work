---
## Front matter
lang: ru-RU
title: Операционные системы
subtitle: Планировщики событий
author:
  - Вишняков Родион Сергеевич
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 24 октября

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: Madrid
---

# Цели и задачи работы

## Цель лабораторной работы

Получение навыков работы с планировщиками событий cron и at.

# Процесс выполнения лабораторной работы

## Получаем полномочия администратора

![root](image/1.png){ #fig:001 width=70% height=70% }

## Посмотрели статус демона crond

![Статус crond](image/2.png){ #fig:002 width=70% height=70% }

## Посмотрели содержимое файла конфигурации /etc/crontab

![Файл конфигурации](image/3.png){ #fig:003 width=70% height=70% }

## Посмотрели список заданий в расписании

![Список заданий](image/4.png){ #fig:004 width=70% height=70% }

## Открыли файл расписания и добавили предоставленную строку

![Файл расписания](image/5.png){ #fig:005 width=70% height=70% }

## Посмотрели список заданий в расписании

![Список заданий](image/6.png){ #fig:005 width=70% height=70% }

## Просмотрели журнал системных событий

![Журнал системных событий](image/7.png){ #fig:005 width=70% height=70% }

## Изменили запись в расписании crontab

![Запись в crontab](image/8.png){ #fig:006 width=70% height=70% }

## Посмотрели список заданий в расписании

![Список заданий](image/9.png){ #fig:006 width=70% height=70% }

## Перешли в каталог /etc/cron.hourly и создали в нём файл сценария с именем eachhour

![Создание файла сценария](image/10.png){ #fig:007 width=70% height=70% }

## Открыли файл eachhour для редактирования и прописали в нём предоставленный скрипт

![Файл eachhour](image/11.png){ #fig:007 width=70% height=70% }

## Сделали файл сценария eachhour исполняемым

![Файл eachhour](image/12.png){ #fig:007 width=70% height=70% }

## Перешли в каталог /etc/crond.d и создали в нём файл с расписанием eachhour

![Файл eachhour](image/13.png){ #fig:008 width=70% height=70% }

## Просмотрели журнал системных событий

![Журнал системных событий](image/14.png){ #fig:009 width=70% height=70% }
 
## Получаем полномочия администратора

![root](image/1.png){ #fig:001 width=70% height=70% }

## Проверили, что служба atd загружена и включена

![Служба atd](image/15.png){ #fig:009 width=70% height=70% }

## Задали выполнение команды logger message from at в 14:21

![logger message from at](image/16.png){ #fig:009 width=70% height=70% }

## Убедились, что задание действительно запланировано

![Запланированное задание](image/17.png){ #fig:009 width=70% height=70% }

# Выводы по проделанной работе

## Вывод

Мы получили навыки работы с планировщиками событий cron и at

