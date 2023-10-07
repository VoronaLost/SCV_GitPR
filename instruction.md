![Лого Git](Git-Logo-White.png)
# Инструкция по основам работы с Git

## 1. Предварительная настройка в VS Code и проверка установленного Git
Запускаем **VS Code** и выполняем предварительные настройки:

 - Открываем консоль терминала: 
>либо через верхнюю панель в меню:
Terminal &rArr;  New Terminal  
либо через сочетание клавиш: <kbd>CTRL</kbd> + <kbd>SHIFT</kbd> + <kbd>`</kbd>  
    
*Есть возможность выбрать различные терминалы в зависимости от предпочтений из выпадающего меню* &#709; *в правой части панели терминала (GitBash, PowerShell)*  
>&#128161; *Свернуть и развернуть панель терминала можно в любой момент сочетеанием клавиш* <kbd>CTRL</kbd> + <kbd>`</kbd>
 - Для удобства работы включим автосохранение файлов в меню программы:  
> Верхняя панель меню - File &rArr; &#10004; Auto Save
   
>&#128161; *При выключенном автосохранении сохранение файла происходит через сочетание клавиш* <kbd>CTRL</kbd> + <kbd>S</kbd> , статус несохраненного файла отображается во вкладке значком &#9675;
 - Проверим наличие установленного Git введя на терминале команду:  
>`git --version`  

в случае если в консоли отобразилась команда с текущей версией, к примеру:
>`git version 2.42.0.windows.2`

то делаем вот такое лицо &#128516;, и переходим к настройке GIT

&#128683; *если в консоли отобразилась сообщение об ошибке, то переходим на официальный [сайт](https://git-scm.com/) Git и скачиваем последнюю версию дистрибутива для нашей операционной системы и устанавливаем его с настройками по умолчанию. После перезапускаем VS Code и вновь проверяем наличие GIT.*

## 2. Настройка Git

- При первом использовании Git необходимо представиться. Для этого вводим в терминале две команды:  
>`git config --global user.email "Ваш адрес электронной почты буквами"`

>`git config --global user.name "Ваше имя английскими буквами"`

>&#128161; *Для просмотра всех текущих настроек пользователя и конфигурации вводим комманду:*  
>`git config --global --list`

>&#128161; *Для скроллинга строк меню терминала, которые не помещаются в окне используйте клавиши* <kbd>Page Up</kbd> *и* <kbd>Page Down</kbd>, *для возвращения в режим набора команд используйте клавишу* <kbd>q</kbd>

- Переходим в папку, в которой планируем работать:
>Открываем в меню File &rArr; Open Folder...  
или набираем на клавиатуре: <kbd>CTRL</kbd>+<kbd>k</kbd> &rArr; <kbd>CTRL</kbd> + <kbd>o</kbd>

## 3. Инициализация репозитория
- Для создания репозитория в текущей папке прописываем комманду:
>`git init`

>&#128161; *После создания репозитория Git создаст в текущей папке скрытый каталог, где будут прописываться все изменения с созданными файлами*

- После создания каталога в качестве примера работы создадим новый файл с расширением .md через меню VS Code:
> File &rArr; New File  
или <kbd>CTRL</kbd>+<kbd>ALT</kbd> + <kbd>Windows</kbd>+<kbd>n</kbd>  
или нажав на пиктограмму папки &#128194;+ в верхнем левом углу при наведении мыши

>&#128161; После создания файла откроется окно редактирования.

>&#128161; *При создании md-файла появляется дополнительное меню предварительного просмотра со значком лупы &#128270;, где можно будет увидеть файл в отформатированном виде.*

## 4. Запись и изменения в разделе репозитория

- После создания новых файлов и внесения в них изменений, нам необходимо начать отслеживать и подготавливать к записи их новые версии, для этого воспользуемся командой:

>`git add. \<имя_файла>`  
*для более сокращенной формы вызова команды достаточно начать набирать первые 4 символа в имени файла и затем нажать клавишу* <kbd>TAB</kbd> *, и консоль автоматически будет дополнять команду с подходящем именем файла в репозитории:*  
>`git add inst` + <kbd>TAB</kbd>  
в результате автозаполнения получится строка:  
>`git add .\instruction.md`

- Для сохранения нового состояния файла (коммиту) необходимо воспользоваться командой:
>`git commit -m "Ваш комментарий к новому коммиту"`  
*После выполнения данной команды во вкладке с файлом пропадет значок M (модифицированный) и в боковой панели исчезнет напоминание о том что есть несохраненные изменения в файле*

- Для просмотра статуса текущего файла и возможных для сохранения коммитов воспользуемся командой
>`git status`  

а для сравнения текущей рабочей версии файла с последним коммитом воспользуемся командой:
>`git diff` 

>&#128161; *Для более быстрого сохранения коммитов можно объединить команды `git add.` и `git commit` в одну:*  
>`git commit -a -m "Ваш комментарий к коммиту"`  
*Стоит помнить что в этом случае мы не прописываем имя файла, и сохраняется всё состояние репозитория*

## 5. Просмотр истории и перемещения между разделами

- Для просмотра истории всех сохраненных коммитов воспользуемся командой:  
`git log`
>&#128161; *После введеной команды в консоли выводится список всех коммитов, где содержится код, автор изменений, дата, и комментарий. Помните, что для просмотра всех коммитов, следует воспользоваться клавишами* <kbd>Page Up</kbd> *и* <kbd>Page Down</kbd>

- Для перехода к предыдущему коммиту воспользуемся операцией:

>`git checkout` "код коммита"  
&#128161; *При вызове этой команды можно тоже воспользоваться автозаполнением и набрать имя файла не полностью, в этом случае, git сам найдет необходимый коммит подходящий под запрос*
- Для возвращения к самой последней сохраненной версией коммита воспользуемся командой:  
>`git checkout master`  
*или*  
>`git switch-`

>&#128161; *Для исправления описания последнего коммита можно воспользоваться командой:*  
`git commit --amend -m "Исправленный комментарий"`

## 6. Игнорирование файлов

Для того, чтобы исключить из отслеживания в репозитории определённые файлы или папки необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны соответствующие такий файлам или папкам.
- Для примера работы файла **.gitignore** скопируем в нашу папку с репозиторием файл изображения Git-Logo-White.png, после чего в случае если .gitignore остался незаполненным, файл изображения будет помечаться как неотслеживаемый.
>&#128161; *При работе в Git не принято отслеживать те файлы, которые не редактируются напрямую, и всю служебную информацию (например изображения) принято делать скрытыми.*  

>*Для демонстрации наличия файла внутри нашего репозитория вставим изображение в начало нашей инструкции перед заголовком, воспользуевшись форматированием Markdown:*  
`![Лого Git](Git-Logo-White.png)`
- внесём в файл .gitignore следующий шаблон:   
`*.png`  
и добавим файл .gitignore в отслеживаемые и сделаем соответствующий коммит:  
> `git add \.gitignore`

> `git commit -m "Добавили .gitignore в отслеживаемое"`

>&#128161; *После выполнения всех операций, файл Git-Logo-White.png в левой части панели VS Code окрасится в серый цвет, и файл перестанет отмечаться как неотслеживаемый. То что файл теперь игнорируется можно проверить командой:*  
`git status`

## 7. Создание веток в Git

- По умолчанию имя основной ветки в git: `master`

>&#128161; *Создать ветку можно командой:*  
`git branch <имя_новой_ветки>`

>&#128161;  Список веток в репозитории можно посмотреть с помощью команды:  
`git branch`  
*Текущая ветка будет отмечена звёздочкой:*  
`*master`

- Для переключение между ветками воспользуемся командой:  
`git checkout <имя_ветки>`
или `git switch <имя_ветки>`

>&#128161; *Для сокращенного вызова, когда нам требуется сразу перейти на созданную ветку можно воспользоваться командами*  
`git checkout -b <имя_новой_ветки>` или `git switch -c <имя_новой_ветки>`

- Для работы с пунктами инструкции создадим 4 дополнительные ветки с именами:  
`create_branch` , `merge_conflict` , `delete`, `corrections` и будем выполнять заполнение инструкции в этих вспомогательных ветках.

## 8. Слияние веток разрешение конфликтов

- После заполнения пунктов инструкции в ветках `create_branch` , `merge_conflict` , `merge_delete` , `corrections`, делаем коммиты с соответствующими комменатриями, и переключишвись на основную ветку `main` воспользуемся командой слияния:  
>`git merge <имя_ветки_с_которой_будет_происходить_слияние>`  
>&#128161; *Для создания конфликтов мы будем дополнительно параллельно делать записи в основной ветки* `main`*, для работы с редактором git по разрешению конфликтов версий*

- Если в ходе слияния не возникло конфликтов записей то git покажет соообщение о выполненной операции, если же возникнут конфликт, то откроется меню по разрешению разных записей в одних и тех же строках:
    - **Accept Current Change** — принять версию из ветки в которой мы сейчас находимся.
    - **Accept Incoming Cnahge** — принять версию из ветки с которой происходит слияние.
    - **Accept Both Changes** — принять различающиеся версии строк из обоих веток (с разделителем между ними)
    - **Сompare Changes** — открыть превью обоих веток для сревниния (совпадающие строки будут подсвечены)

>&#128161; *После разрешение всех конфликтов слияния в окне редактора, для утверждения всех изменений следует сделать коммит, после чего на панели VS Code пропадет красное предупреждение.*

## 9. Просмотр дерева коммитов в виде графов и удаление веток
- После того как мы выполним заполнение всех пунктов в дополнительных ветках и произведем их слияние с основной, просмотрим то как выглядит дерево коммитов. Для этого выполним расширенную команду:
`git log --graph` 
>&#128161; *Данная команда покажет всю ветку коммитов относительно текущей ветки, и где в этом дереве находятся коммиты прошлых сохранений других веток (если такие имеются)*

>&#128161; *Также для команд `git log` и `git log --graph`, есть версии более компактной формы отображения логов без пропусков строк:

>`git log --oneline`  

>`git log --graph --oneline`

- По завершению заполнения инструкции, и слиянии вспомогательных веток с основной, нам потребуется избавиться уже от ненужных веток, и удалить их. Для этого воспользуемся командой:

>`git branch -d <имя_удаляемой_ветки>`  
&#128161; *Данная команда удаляет те ветки, с которыми уже было произведено слияние, для принудительного удаления веток следует исспользовать команду:*  
>`git branch -D <имя_удаляемой_ветки>`  
&#128161; *Стоит также помнить что нельзя удалить ту ветку, в которой мы сейчас находимся.*

## 10. Заключение

- В ходе заполнения инструкции мы изучили основы работы в Git, а также разобрали основые команды и принципы работы с системой контроля версий.

>&#128161; *Для просмотра списка команд в Git можно воспользоваться встроенным помощником вызвав команду:*  
`git help--`


    