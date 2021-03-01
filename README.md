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
14. echo "test1" > second_branch.txt
15. git add *
16. git commit -m "test_second_branch"
17. git checkout second
18. echo "test2" > second_branch2.txt
19. git add *
20. git commit -m "test_second_branch2" намудрил с названиями веток и коммитов
21. git branch 
22. git merge first изменения указанной ветки в текущую ветку "second > first"
23. git log
commit 48440eafd480e65a42d07b3c7a65c95343ebc6f8 (HEAD -> second)
Merge: c2589f5 44aaf8c
Author: Maxim <man2013@gmail.com>
Date:   Mon Mar 1 19:05:18 2021 +0000

    Merge branch 'first' into second
    "second > first"

commit c2589f5453eb238dcd6dc80ed6ec9b8221ea3954
Author: Maxim <man2013@gmail.com>
Date:   Mon Mar 1 18:59:52 2021 +0000

    test_second_branch2

commit 44aaf8c800a390da62d68c8be6207558b46ef55a (first)
Author: Maxim <man2013@gmail.com>
Date:   Mon Mar 1 18:53:12 2021 +0000

    test_second_branch

commit 64627119d59b927240b21cfecdd2ba0e4aeb5626 (master)
Author: Maxim <man2013@gmail.com>
Date:   Mon Mar 1 18:22:54 2021 +0000
