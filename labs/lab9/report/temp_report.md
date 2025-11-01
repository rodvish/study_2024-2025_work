---
## Front matter
title: "Отчёт по лабораторной работе 9"
subtitle: "Управление SELinux"
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

Получить навыки работы с контекстом безопасности и политиками SELinux.

# Выполнение лабораторной работы

Получаем полномочия администратора

![root](image/1.png){ #fig:001 width=70% height=70% }

Просмотрели текущую информацию о состоянии SELinux

![SELinux](image/2.png){ #fig:002 width=70% height=70% }

Посмотрели, в каком режиме работает SELinux

![SELinux](image/3.png){ #fig:003 width=70% height=70% }

В файле /etc/sysconfig/selinux с помощью редактора установили заданное значение

![Изменение редактора](image/4.png){ #fig:004 width=70% height=70% }

Посмотрели статус SELinux

![SELinux](image/5.png){ #fig:005 width=70% height=70% }

Попробовали переключить режим работы SELinux

![SELinux](image/6.png){ #fig:005 width=70% height=70% }

В файле /etc/sysconfig/selinux с помощью редактора установили заданное значение

![Изменение редактора](image/7.png){ #fig:005 width=70% height=70% }

Просмотрели текущую информацию о состоянии SELinux

![SELinux](image/8.png){ #fig:006 width=70% height=70% }

Посмотрели контекст безопасности файла /etc/hosts

![Контекст безопасности файла](image/9.png){ #fig:006 width=70% height=70% }

Скопировали файл /etc/hosts в домашний каталог и проверили контекст файла ~/hosts

![Создание файла сценария](image/10.png){ #fig:007 width=70% height=70% }

Попытались перезаписать существующий файл hosts из домашнего каталога в ката-
лог /etc

![Файл hosts](image/11.png){ #fig:007 width=70% height=70% }

Убедились, что тип контекста по-прежнему установлен на admin_home_t

![admin_home_t](image/12.png){ #fig:007 width=70% height=70% }

Исправили контекст безопасности

![Контекст безопасности](image/13.png){ #fig:008 width=70% height=70% }

Убедились, что тип контекста изменился

![Тип контекста](image/14.png){ #fig:009 width=70% height=70% }
 
Для массового исправления контекста безопасности на файловой системе ввели

![Массовое исправления контекста](image/15.png){ #fig:001 width=70% height=70% }

Получаем полномочия администратора

![root](image/16.png){ #fig:001 width=70% height=70% }

Установливаем необходимое программное обеспечение

![Необходимое программное обеспечение](image/17.png){ #fig:009 width=70% height=70% }

Создали новое хранилище для файлов web-сервера

![Новое хранилище](image/18.png){ #fig:009 width=70% height=70% }

Создали файл index.html в каталоге с контентом веб-сервера и поместили в файл следующий текст

![index.html](image/19.png){ #fig:009 width=70% height=70% }

Проделываем различные действия со строками в файле /etc/httpd/conf/httpd.conf

![/etc/httpd/conf/httpd.conf](image/20.png){ #fig:009 width=70% height=70% }

Запустили веб-сервер и службу httpd

![Служба httpd и веб-сервер](image/21.png){ #fig:009 width=70% height=70% }

Обратились к веб-серверу в текстовом браузере lynx

![lynx](image/22.png){ #fig:009 width=70% height=70% }

В терминале с полномочиями администратора применили новую метку контекста к /web

![Новая метку контекста к /web](image/23.png){ #fig:009 width=70% height=70% }

Восстановили контекст безопасности

![Контекст безопасности](image/24.png){ #fig:009 width=70% height=70% }

Снова обращаемся к веб-серверу

![Веб-сервер](image/25.png){ #fig:009 width=70% height=70% }

Посмотрели список переключателей SELinux для службы ftp

![Список переключателей SELinux](image/26.png){ #fig:009 width=70% height=70% }

Посмотрели список переключателей с пояснением

![Список переключателей с пояснением](image/27.png){ #fig:009 width=70% height=70% }

Изменили текущее значение переключателя для службы ftpd_anon_write с off на on

![Значение переключателя](image/28.png){ #fig:009 width=70% height=70% }

Повторно посмотрели список переключателей SELinux для службы ftpd_anon_write

![Список переключателей SELinux](image/29.png){ #fig:009 width=70% height=70% }

Изменили постоянное значение переключателя для службы ftpd_anon_write с off на on

![Постоянное значение переключателя](image/30.png){ #fig:009 width=70% height=70% }

Посмотрели список переключателей

![Список переключателей](image/31.png){ #fig:009 width=70% height=70% }


# Вывод

Мы получили навыки работы с контекстом безопасности и политиками SELinux.

# Контрольные вопросы

1. Вы хотите временно поставить SELinux в разрешающем режиме. Какую команду вы используете?
   Ответ: Команда setenforce 0.

2. Вам нужен список всех доступных переключателей SELinux. Какую команду вы используете?
   Ответ: Команда getsebool -a.

3. Каково имя пакета, который требуется установить для получения легко читаемых сообщений журнала SELinux в журнале аудита?
   Ответ: Имя пакета setroubleshoot.

4. Какие команды вам нужно выполнить, чтобы применить тип контекста httpd_sys_content_t к каталогу /web?
   Ответ: Команда chcon -t httpd_sys_content_t /web или команды semanage fcontext -a -t httpd_sys_content_t '/web(/.*)?' и затем restorecon -Rv /web.

5. Какой файл вам нужно изменить, если вы хотите полностью отключить SELinux?
   Ответ: Файл /etc/selinux/config.

6. Где SELinux регистрирует все свои сообщения?
   Ответ: В журнале аудита /var/log/audit/audit.log и в системном журнале /var/log/messages.

7. Вы не знаете, какие типы контекстов доступны для службы ftp. Какая команда позволяет получить более конкретную информацию?
   Ответ: Команда sepolicy ftp или semanage boolean -l | grep ftp.

8. Ваш сервис работает не так, как ожидалось, и вы хотите узнать, связано ли это с SELinux или чем-то ещё. Какой самый простой способ узнать?
   Ответ: Временно перевести SELinux в разрешающий режим с помощью команды setenforce 0 и проверить, исчезла ли проблема.
