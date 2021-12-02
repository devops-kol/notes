## Git ##

**Настройки git**
| git config --global user.name ""
| git config --global user.email

**Инициализация репозитория**
| git init

**Добавить файлы в список отслеживаемых**
| git add file_name

**Сделать коммит**
git commit -m "Init commit"

**Добавить файлы в список игнорированных**
touch .gitignore

**Посмотреть разницу между версиями коммитов**
git diff

**Добавить удаленный репозиторий в свой проект**
git remote add origin "http://..."

**Отправить изменения в удаленный репо**
git push origin master

**Последовательная история коммитов**
git log --graph

**Влить изменения из ветки dev**
git merge dev
