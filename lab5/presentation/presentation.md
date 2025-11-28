---
## Front matter
lang: ru-RU
title: Операционные системы
subtitle: Управление системными службами
author:
  - Вишняков Родион Сергеевич
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 22 ноября 2025

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

Получить навыки управления системными службами операционной системы посредством systemd.

# Процесс выполнения лабораторной работы

## Получаем полномочия администратора

![root](image/1.png){ #fig:001 width=70% height=70% }

## Проверяем статус службы Very Secure FTP

![Проверка статуса службы](image/2.png){ #fig:002 width=70% height=70% }

## Установка службы Very Secure FTP

![Установка](image/3.png){ #fig:003 width=70% height=70% }

## Запускаем службу Very Secure FTP

![Пуск](image/4.png){ #fig:004 width=70% height=70% }

## Проверяю статус службы Very Secure FTP

![Проверка](image/5.png){ #fig:005 width=70% height=70% }

## Добавляю службу Very Secure FTP в автозапуск, проверяю статус, удаляю службу и снова проверяю статус

![Работа со службой](image/6.png){ #fig:005 width=70% height=70% }

## Вывожу на экран символические ссылки

![Вывод на экран](image/7.png){ #fig:005 width=70% height=70% }

## Снова добавляю службу Very Secure FTP в автозапуск

![Служба Very Secure FTP](image/8.png){ #fig:006 width=70% height=70% }

## Проверяю статус службы Very Secure FTP

![Статус Very Secure FTP](image/9.png){ #fig:006 width=70% height=70% }

## Вывожу на экран список зависимостей юнита

![Список зависимостей юнита](image/10.png){ #fig:007 width=70% height=70% }

## Вывожу на экран список юнитов

![Список юнитов](image/11.png){ #fig:007 width=70% height=70% }

## Установка iptables

![Установка](image/12.png){ #fig:007 width=70% height=70% }

## Проверяю статус

![Статус](image/13.png){ #fig:008 width=70% height=70% }

## Пробую запустить firewalld и iptables

![Запуск](image/24.png){ #fig:009 width=70% height=70% }
 
## Ввод команды

![Настройки конфликтов](image/14.png){ #fig:010 width=70% height=70% }

## Ввод команды

![Настройки конфликтов](image/25.png){ #fig:010 width=70% height=70% }
 
## Выгружаю службу iptables и загружаю службу firewalld

![Выгрузка и загрузка службы](image/15.png){ #fig:011 width=70% height=70% }

## Заблокирую запуск iptables

![Блокировка запуска](image/26.jpg){ #fig:012 width=70% height=70% }

## Пробую запустить iptables:

![Попытка запуска](image/16.png){ #fig:013 width=70% height=70% }
 
## Пробую добавить iptables в автозапуск

![Попытка добавить iptables в автозапуск](image/17.png){ #fig:014 width=70% height=70% }

## Перехожу в каталог systemd и нахожу список всех целей, которые можно изолировать

![Поиск необходимых целей](image/18.png){ #fig:015 width=70% height=70% }

## Переключаю операционную систему в режим восстановления

![Режим восстановления](image/19.jpg){ #fig:015 width=70% height=70% }

## Перезапускаю ОС

![Перезапуск ОС](image/20.jpg){ #fig:015 width=70% height=70% }

## Вывожу на экран цель, установленную по умолчанию

![Цель](image/21.png){ #fig:015 width=70% height=70% }

## Запускаю текстовый режим

![Запуск текстового режима](image/22.jpg){ #fig:016 width=70% height=70% }

## Запускаю графический режим

![Запуск графического режима](image/23.jpg){ #fig:015 width=70% height=70% }

# Выводы по проделанной работе

## Вывод

Мы получили навыки управления системными службами операционной системы посредством systemd.


