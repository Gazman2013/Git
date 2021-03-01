# Git
1. Создать отдельный репозиторий на github.
2. Создать локально три текстовых файла.
3. Поместить в стейдж, закомитить, запушить.
4. Создать две новые ветки.
5. Внести изменения в ветку 1 и 2 
6. Смерджить между собой вновь созданные ветки.
7. Смерджить ветку с веткой мастер
8. Отменить предыдущий комит
9. Все изменения запушить в гит репозиторий.

1. mkdir dev
2. cd dev
3. touch HW1.txt HW2.txt HW3.txt
4. git status
5. git add * начать отслеживать (добавить под версионный контроль) новые файлы
6. root@instance-3:/home/dev# git status определяем состояние файлов
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   HW1.txt
        new file:   HW2.txt
        new file:   HW3.txt

7. git commit -m "test commit" фиксация изменений
[master (root-commit) 6462711] test commit
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 dev/HW1.txt
 create mode 100644 dev/HW2.txt
 create mode 100644 dev/HW3.txt

8.  git push https://github.com/
Enumerating objects: 4, done.
9. git branch список веток
10. git branch first создание веток
11. git branch second
12. git branch
first
master
second
13.  git checkout first переключение на выбраную ветку
Switched to branch 'first'
14. git branch
* first
  master
  second
