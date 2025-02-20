# Что такое Git и зачем он нужен?
Git - это консольная утилита, для отслеживания и ведения истории изменения файлов, в вашем проекте. Чаще всего его используют для кода, но можно и для других файлов. Например, для картинок - полезно для дизайнеров.

С помощью Git-a вы можете откатить свой проект до более старой версии, сравнивать, анализировать или сливать свои изменения в репозиторий.

Репозиторием называют хранилище вашего кода и историю его изменений. Git работает локально и все ваши репозитории хранятся в определенных папках на жестком диске.

Так же ваши репозитории можно хранить и в интернете. Обычно для этого используют три сервиса:

* GitHub

* itbucket

* GitLab

Каждая точка сохранения вашего проекта носит название коммит (commit). У каждого commit-a есть hash (уникальный id) и комментарий. Из таких commit-ов собирается ветка. Ветка - это история изменений. У каждой ветки есть свое название. Репозиторий может содержать в себе несколько веток, которые создаются из других веток или вливаются в них.

## Настройка

Вы установили себе Git и можете им пользоваться. Давайте теперь его настроим, чтобы когда вы создавали commit, указывался автор, кто его создал.

Открываем терминал (Linux и MacOS) или консоль (Windows) и вводим следующие команды.

Установим имя для вашего пользователя

**git config --global user.name "<ваше_имя>"**

Теперь установим email. 
Принцип тот же.

**git config --global user.email "<адрес_почты@email.com>"**

## Создание репозитория

Создадим репозиторий. Для этого пройдите в папку вашего проекта.

Для Linux и MacOS путь может выглядеть так 
/Users/UserName/Desktop/MyProject

Для Windows например С://MyProject
cd <путь_к_вашему_проекту>

### Инициализация/создание репозитория

**git init**

Теперь Git отслеживает изменения файлов вашего проекта. Но, так как вы только создали репозиторий в нем нет вашего кода. Для этого необходимо создать commit.

*Добавим все файлы проекта в нам будующий commit*
git add .

Или так

git add --all

Если хотим добавить конкретный файл то можно так
git add <имя_файла> 

Теперь создаем commit.

Обязательно указываем комментарий.
И не забываем про кавычки
git commit -m "<комментарий>"

## Для того, чтобы создать новую ветку вводим:

**git branch <название_ветки>**

или вот так

**git checkout -b <название_ветки>**

### Вспомогательные команды
Просмотреть изменения относительно двух веток можно командой:

**git diff <исходная_ветка> <целевая_ветка>**

Удалить ненужную ветку:

**git branch -d <название_ветки>**

Просмотр историю ветки:

**git log**


## Переключаться между ветками можно такой командой:

**git checkout <название_ветки>**

Переключаемся в master
**git checkout master**

### Делаем merge вашей ветки, в ветку в которой вы находитесь В данном примере это master
**git merge <название_ветки>**

Подсказки по популярным командам:

## По популярным командам
git help

## Или по конкретной команде
git help <название_команды>

## Например clone
git help clone

## Удалённые репозитории

Есть два распространённых способа привязать удалённый репозиторий к локальному: по HTTPS и по SSH. Если SSH у вас не настроен (или вы не знаете что это), привязывайте удалённый репозиторий по HTTPS (адрес привязываемого репозитория должен начинаться с https://).

**git remote -v               показать список удалённых репозиториев, связанных с локальным**

**git branch -r               показать удаленные ветки**

**git branch -a               показать все ветки(локальные и удаленные)**       

*git remote remove origin    убрать привязку удалённого репозитория с сокр. именем origin*

**git remote add origin https://github.com:nicothin/test.git  добавить удалённый репозиторий (с сокр. именем origin) с указанным URL**

**git remote rm origin        удалить привязку удалённого репозитория**

**git remote show origin      получить данные об удалённом репозитории с сокращенным именем origin**

**git fetch origin            скачать все ветки с удаленного репозитория (с сокр. именем origin), но не сливать со своими ветками**

**git fetch origin master    то же, но скачивается только указанная ветка**

**git checkout --track origin/github_branch  создать локальную ветку github_branch (данные взять из удалённого репозитория с сокр. именем origin, ветка github_branch) и переключиться на неё**

**git push origin master      отправить в удалённый репозиторий (с сокр. именем origin) данные своей ветки master**

**git pull origin             влить изменения с удалённого репозитория (все ветки)**

**git pull origin master      влить изменения с удалённого репозитория (только указанная ветка)**