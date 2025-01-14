# Домашнее задание к занятию «Инструменты Git» - Сергей Яремко

### Цель задания

В результате выполнения задания вы:

* научитесь работать с утилитами Git;
* потренируетесь решать типовые задачи, возникающие при работе в команде. 

### Инструкция к заданию

1. Склонируйте [репозиторий](https://github.com/hashicorp/terraform) с исходным кодом Terraform.
2. Создайте файл для ответов на задания в своём репозитории, после выполнения прикрепите ссылку на .md-файл с ответами в личном кабинете.
3. Любые вопросы по решению задач задавайте в чате учебной группы.

------

## Задание

В клонированном репозитории:

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на `aefea`.

```
git show aefea
```
![](https://github.com/s-bessonniy/sysadm-homeworks/blob/devsys10/02-git-04-tools/img/VirtualBox_Ubuntu-50Gb_29_09_2024_13_43_22.png)


2. Ответьте на вопросы.

* Какому тегу соответствует коммит `85024d3`?

```
git log -1 85024d3
```
![](https://github.com/s-bessonniy/sysadm-homeworks/blob/devsys10/02-git-04-tools/img/VirtualBox_Ubuntu-50Gb_29_09_2024_14_07_52.png)

* Сколько родителей у коммита `b8d720`? Напишите их хеши.

```
git log -1 b8d720 - сокращенный вывод

git log --pretty=%P -n 1 b8d720

или

git show -s --pretty=%P b8d720
```
![](https://github.com/s-bessonniy/sysadm-homeworks/blob/devsys10/02-git-04-tools/img/VirtualBox_Ubuntu-50Gb_29_09_2024_14_15_50.png)

* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами  v0.12.23 и v0.12.24.

```
git log v0.12.23..v0.12.24 --pretty=oneline
```
![](https://github.com/s-bessonniy/sysadm-homeworks/blob/devsys10/02-git-04-tools/img/VirtualBox_Ubuntu-50Gb_29_09_2024_14_18_58.png)

* Найдите коммит, в котором была создана функция `func providerSource`, её определение в коде выглядит так: `func providerSource(...)` (вместо троеточия перечислены аргументы).

```
git log -S 'func providerSource'
```
![](https://github.com/s-bessonniy/sysadm-homeworks/blob/devsys10/02-git-04-tools/img/VirtualBox_Ubuntu-50Gb_29_09_2024_14_21_32.png)

* Найдите все коммиты, в которых была изменена функция `globalPluginDirs`.

```
git log -GglobalPluginDirs --stat
```
![](https://github.com/s-bessonniy/sysadm-homeworks/blob/devsys10/02-git-04-tools/img/VirtualBox_Ubuntu-50Gb_29_09_2024_14_25_23.png)

* Кто автор функции `synchronizedWriters`?

```
git log -S synchronizedWriters --pretty=format:"%h %an"
```
![](https://github.com/s-bessonniy/sysadm-homeworks/blob/devsys10/02-git-04-tools/img/VirtualBox_Ubuntu-50Gb_29_09_2024_14_27_37.png)

*В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.*

---

### Правила приёма домашнего задания

В личном кабинете отправлена ссылка на .md-файл в вашем репозитории.

### Критерии оценки

Зачёт:

* выполнены все задания;
* ответы даны в развёрнутой форме;
* приложены соответствующие скриншоты и файлы проекта;
* в выполненных заданиях нет противоречий и нарушения логики.

На доработку:

* задание выполнено частично или не выполнено вообще;
* в логике выполнения заданий есть противоречия и существенные недостатки.
