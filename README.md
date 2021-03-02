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
git branch one
git branch two
git checkout one
echo "test1" > one.txt
git add .
git commit -m "Edit one.txt"
[one 527ec6b] Edit one.txt
 1 file changed, 1 insertion(+)
 create mode 100644 dev/one.txt


git checkout two
git checkout two
Switched to branch 'two'
echo "test2" > two.txt
git add .
git commit -m "Edit two.txt"
[two f34c591] Edit two.txt
 1 file changed, 1 insertion(+)
 create mode 100644 dev/two.txt
--------------------------------
git log -n 2 --graph --all
* commit f34c591bfd3d757af4d2b375a390c2926961deb9 (HEAD -> two)
| Author: Maxim <rodionov.gazman2013@gmail.com>
| Date:   Tue Mar 2 07:22:25 2021 +0000
|
|     Edit two.txt
|
| * commit 527ec6b4db14840f38eac7545ab3699f5ea5dc0e (one)
|/  Author: Maxim <rodionov.gazman2013@gmail.com>
|   Date:   Tue Mar 2 07:21:14 2021 +0000
|
|       Edit one.txt

------------------------------------
git merge one  -m "Merge two with one"
Merge made by the 'recursive' strategy.
 dev/one.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 dev/one.txt

---------------------------------------------
git log -n 1 --graph --all
*   commit 25267fc49824ef1436df50ae050010af6c030fc8 (HEAD -> two)
|\  Merge: f34c591 527ec6b
| | Author: Maxim <rodionov.gazman2013@gmail.com>
| | Date:   Tue Mar 2 07:27:44 2021 +0000
| |
| |     Merge two with one


-------------------------------------------
git checkout master
git merge two -m "Merge master with two"
Updating 44aaf8c..25267fc
Fast-forward (no commit created; -m option ignored)
 dev/one.txt | 1 +
 dev/two.txt | 1 +
 2 files changed, 2 insertions(+)
 create mode 100644 dev/one.txt
 create mode 100644 dev/two.txt
------------------------------------------
git log -n 2 --graph --all
*   commit 25267fc49824ef1436df50ae050010af6c030fc8 (HEAD -> master, two)
|\  Merge: f34c591 527ec6b
| | Author: Maxim <rodionov.gazman2013@gmail.com>
| | Date:   Tue Mar 2 07:27:44 2021 +0000
| |
| |     Merge two with one
| |
| * commit 527ec6b4db14840f38eac7545ab3699f5ea5dc0e (one)
| | Author: Maxim <rodionov.gazman2013@gmail.com>
| | Date:   Tue Mar 2 07:21:14 2021 +0000
| |
| |     Edit one.txt
---------------------------------------------
git reset --hard HEAD~1
HEAD is now at f34c591 Edit two.txt
git log -n 2 --graph --all
*   commit 25267fc49824ef1436df50ae050010af6c030fc8 (two)
|\  Merge: f34c591 527ec6b
| | Author: Maxim <rodionov.gazman2013@gmail.com>
| | Date:   Tue Mar 2 07:27:44 2021 +0000
| |
| |     Merge two with one
| |
| * commit 527ec6b4db14840f38eac7545ab3699f5ea5dc0e (one)
| | Author: Maxim <rodionov.gazman2013@gmail.com>
| | Date:   Tue Mar 2 07:21:14 2021 +0000
| |
| |     Edit one.txt

----------------------------------------------
master/git/dev
HW1.txt
test commit
13 hours ago
HW2.txt
test commit
13 hours ago
HW3.txt
test commit
13 hours ago
second_branch.txt
test_second_branch
13 hours ago
two.txt
Edit two.txt
12 minutes ago
