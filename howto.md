Клонируем
```
git clone https://github.com/Otkuda/KotlinAsFirst2020`
cd KotlinAsFirst2020
```
Добавляем апстрим
```
git remote add upstream-my https://github.com/Otkuda/KotlinAsFirst2021
git fetch upstream-my
```
Создаем ветку backport и заодно переходим в нее
```
git checkout -b backport
```
Берем все коммиты с того что указан по конечный и перекидываем в текущую ветку
```
git cherry-pick d535f3592006b8f2593c9f881d72c05164aadc13...FETCH_HEAD
```
Добавляем второй апстрим (своей пары)
```
git remote add upstream-theirs https://github.com/katemelekhina/KotlinAsFirst2021
git fetch upstream-theirs
```
Переходим в ветку master
```
git checkout  master
```
Мерджим
```
git merge upstream-theirs/master backport
```
Исправляем конфликты с vs code
```
git commit // коммитил через vs code
git push
```
Заливаем все что нам выдает git remote -v в файл remotes
```
git remote -v > remotes
```
Добавляем remotes в гит чтобы он за ним следил
```
git add remotes
```
Коммитим и пушим
```
git commit -m "donee"
git push
```
ПРОФИТ