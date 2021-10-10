Домашнее задание к занятию «2.4. Инструменты Git»
=========

1- **Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.**.

commit aefead2207ef7e2aa5dc81a34aedf0cad4c32545

Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>

Date:   Thu Jun 18 10:29:58 2020 -0400
        Update CHANGELOG.md

Коммандой git log aefea --oneline получил информацию о коммите.

2- **Какому тегу соответствует коммит 85024d3**: 

 tag: v0.12.23

Коммандой git show 85024d3 получил информацию о коммите.

3- **Сколько родителей у коммита b8d720? Напишите их хеши.**: 

Merge: 56cd7859e 9ea88f22f

Коммандой git show b8d720 получил информацию о коммите.  

4- **Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.**: 

* 33ff1c03b (tag: v0.12.24) v0.12.24
* b14b74c49 [Website] vmc provider links
* 3f235065b Update CHANGELOG.md
* 6ae64e247 registry: Fix panic when server is unreachable
* 5c619ca1b website: Remove links to the getting started guide's old location
* 06275647e Update CHANGELOG.md
* d5f9411f5 command: Fix bug when using terraform login on Windows
* 4b6d06cc5 Update CHANGELOG.md
* dd01a3507 Update CHANGELOG.md
* 225466bc3 Cleanup after v0.12.23 release
* 85024d310 (tag: v0.12.23) v0.12.23

Коммандой git log v0.12.23^..v0.12.24 --oneline --graph получил выборку коммитов от v0.12.23 до v0.12.24.

5- **Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так func providerSource(...) (вместо троеточего перечислены аргументы).**

хеш 8c928e835

файл provider_source.go

func providerSource(services *disco.Disco)

При помощи комманды git grep -p 'func providerSource' были найден файл. Коммандой git log -L :providerSource:provider_source.go --oneline получил список коммитов, из списка взял первый коммит, где была создана функция.

6- **Найдите все коммиты в которых была изменена функция globalPluginDirs.**

файл plugins.go

func globalPluginDirs()

Хеш:
* 78b122055
* 52dbf9483
* 41ab0aef7
* 66ebff90c
* 8364383c3

При помощи комманды git grep -p 'globalPluginDirs' были найдены  файлы с упоминанием функции. В файле plugins.go была задана функция func globalPluginDirs(). Коммандой git log -L :'func globalPluginDirs':plugins.go --oneline получил список коммитов, где изменялся файл. 


7- **Кто автор функции synchronizedWriters?**

Author: Martin Atkins <mart@degeneration.co.uk>

При помощи команды git log -S synchronizedWriters --oneline были найдены коммиты в которых упоминалось synchronizedWriters. В первом коммите был указан автор.
