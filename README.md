# Lab 01. Version Control Systems (Git)

## Цель

Получить базовые навыки работы с системами контроля версий на примере **git**.

## Общая информация

### Исходные данные

Задания были разработаны таким образом, чтобы Вы смогли на конкретных примерах поработать с гитом через консоль (я использую `PowerShell`). Если у Вас появится желание попробоать все/некоторые шаги с помощью графического приложения, список Вы можете найти ниже. Вам потребуются некоторые файлы, которые вы сможете скачать по [ссылке](https://github.com/YauheniyaSirotkina/git-example/files/12966103/files.zip) (архив `files.zip` должен содержать 5 файлов).

### Критерии

* Имена коммитов должны быть **краткими** и **содержательными**.
* Выполнение всех задач в рамках данного задания не является обязательным, но крайне желательно, т.к. это позволит вам познакомиться с базовыми возможностями `git`а.

## Задание

Ввиду того, что часть заданий зависят друг от друга, их желательно выполнять последовательно, начиная с задачи №1.

### Задача 1. Инициализация репозитория

1. Создайте **git-example** папку в любом месте на вашем жёстком диске (можете назвать по-другому, но желательно, чтобы составное название содержало тире или было без пробелов — git-example или GitExample). Перенесите файлы, которые Вы должны были скачать архивом.
2. Проинициализируйте git-репозиторий в папке **git-example** \(`git init`\).
3. Проверьте статус репозитория при помощи команды `git status`. 
4. Добавьте все файлы в список отслеживаемых для коммита при помощи команды `git add .`.
5. Ещё раз проверьте статус репозитория при помощи команды `git status`.
6. Создайте первый коммит при помощи команды `git commit`. Не забываем про **краткое** и **содержательное** имя коммита.
7. Убедитесь в том, что после выполнения предыдущего шага список отслеживаемых файлов пуст.
8. Убедитесь в том, что Ваш коммит попал в историю коммитов репозитория \(`git log`\).

### Задача 2. Добавление удалённого репозитория \(remote\)

1. Здесь и ниже должен быть использован remote репозиторий, который Вы сами должны будете создать в своём GitHub-аккаунте (в данной ситуации, проще создать новый репозиторий с таким же именем, что и у локального репозитория).
2. Настройте ваш локальный репозиторий из задачи №1 для работы с удалённым репозиторией при помощи команды `git remote add`. Имя remote'a - `origin`.
3. Убедитесь в том, что remote был корректно добавлен при помощи команды `git remote -v`.
4. Отправьте сделанный ранее коммит в удалённый репозиторий при помощи команды `git push` (если репозиторий был создан пустым, то и ветки мастер там не будет и Вы можете воспользоваться коандой `git push --all`).
5. С помощью графического интерфейса в веб-сервисе убедитесь в том, что коммит существует в удалённом репозитории.

### Задача 3. Получение информации из удалённого репозитория

1. Создайте новую, отдельную папку (например, **git-example-2**) и скопируйте в неё содержимое папки **git-example**. Убедитесь в том, что новая папка содержит в себе скрытую директорию **.git**.
2. В рамках **git-example-2** создайте директорию **templates** и переместите туда template-файлы - _index.eex_, _sensors.eex_, _show.eex_.
3. Убедитесь в том, что в репозитории есть изменения при помощи команды `git status`.
4. Создайте коммит с этими изменениями. Следите за именем коммита.
5. Отправьте данный коммит в удалённый репозиторий.
6. Переключитесь на изначальный репозиторий **git-example**.
7. Обновите актуальную информацию об удалённом репозитории при помощи команды `git fetch`.
8. Заберите изменения из удалённого репозитория при помощи команды `git pull`.
9. Убедитесь в том, что коммит с созданием template-директории присутствует локально - `git log`.

### Задача 4. Создание и удаление веток

1. Перейдите в локальный репозиторий **git-example**.
2. Убедитесь в том, что текущая ветка - `master`. Для этого можно использовать команду `git status`.
3. Создайте две новых ветки - `task-branching-01` и `task-branching-02` - от ветки `master`. Для этого необходимо использовать команду `git checkout` с параметром `-b` или команду `git branch`.
4. Проверьте список веток при помощи команды `git branch`.
5. Переключитесь на ветку `task-branching-01` и удалите там файл _about.html_. Создайте коммит со своими изменениями и сохраните его в удалённом репозитории в одноимённой ветке.
6. Теперь переключитесь на ветку `task-branching-02` и проверьте лог при помощи команды `git log`. Убедитесь в том, что файл `about.html` присутствует в репозитории.
7. Создайте в корне репозитория папку **pages** и переместите туда файлы - _about.html_, _faq.md_.
8. Создайте коммит с данными изменениями в рамках `task-branching-02` и сохраните его в удалённом репозитории в одноимённой ветке.
9. Переключитесь на ветку `master`.
10. Удалите локально ветку `task-branching-01`. Для этого можно использовать команду `git branch`. Убедитесь в том, что удалённая ветка по прежнему существует.
11. Удалите локально ветку `task-branching-02`. Убедитесь в том, что ветка с заданным именем существует в удалённом репозитории.
12. Удалите ветку `task-branching-02` в remote при помощи команды `git push`.

### Задача 5. Разрешение конфликтов. Операция `merge`

1. Перейдите в локальный репозиторий **git-example-2**.
2. Убедитесь в том, что текущая ветка - `master`.
3. Создайте две новых ветки - `merge-branch-01` и `merge-branch-02` - от ветки `master`.
4. Переключитесь на ветку `merge-branch-01`, откройте файл _faq.md_ и добавьте в самый конец файла следующий фрагмент текста

   > Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque eleifend nibh vel risus
   > pellentesque, vel molestie purus feugiat. Donec pharetra interdum viverra. Praesent efficitur viverra
   > pante. Suspendisse diam dui, ultrices in tempor vitae, sagittis a metus. Mauris eget felis pellentesque
   > nisi auctor scelerisque in non ex. Nulla fringilla ornare bibendum. Ut et nulla aliquet, tempus enim vel,
   > sodales turpis. Donec tincidunt tincidunt nisl a ultricies. Ut nec purus arcu. Fusce viverra vestibulum
   > arcu sed molestie. Aenean augue lectus, volutpat sit amet est sit amet, maximus ultrices ligula. Etiam
   > placerat urna vel pretium placerat. Quisque ultricies sodales augue a tristique.

5. Создайте коммит с текущими изменениями в файле _faq.md_.
6. Переключитесь на ветку `master` и смержите в неё ветку `merge-branch-01`. Для этого можно использовать команду `git merge`.
7. Убедитесь в том, что операция прошла успешно, при помощи команд `git status` и `git log`.
8. Переключитесь на ветку `merge-branch-02`, откройте файл _faq.md_ и добавьте в самый конец файла следующий фрагмент текста

   > Fusce urna lacus, elementum in rutrum rutrum, ultricies tincidunt ipsum. Donec congue nisl orci.
   > Curabitur tincidunt libero est, in fermentum metus elementum a. Suspendisse eu tellus sit amet
   > lectus accumsan dapibus a ut erat. Aliquam id rutrum eros. In in cursus lectus. Quisque cursus
   > molestie orci non dictum. Praesent aliquam erat sit amet felis varius, vitae congue odio scelerisque.

9. Создайте коммит с текущими изменениями в файле _faq.md_.
10. Переключитесь на ветку `master` и смержите в неё ветку `merge-branch-02`, разрешив конфликты в файле _faq.md_ таким образом, чтобы **lorem ipsum** текст в конце файла выглядел бы следующим образом

    > Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque eleifend nibh vel risus
    > pellentesque, vel molestie purus feugiat. Donec pharetra interdum viverra. Praesent efficitur viverra
    > pante. Suspendisse diam dui, ultrices in tempor vitae, sagittis a metus. Mauris eget felis pellentesque
    > nisi auctor scelerisque in non ex. Nulla fringilla ornare bibendum. Ut et nulla aliquet, tempus enim vel,
    > sodales turpis. Donec tincidunt tincidunt nisl a ultricies. Ut nec purus arcu. Fusce viverra vestibulum
    > arcu sed molestie. Aenean augue lectus, volutpat sit amet est sit amet, maximus ultrices ligula. Etiam
    > placerat urna vel pretium placerat. Quisque ultricies sodales augue a tristique.
    >
    > Fusce urna lacus, elementum in rutrum rutrum, ultricies tincidunt ipsum. Donec congue nisl orci.
    > Curabitur tincidunt libero est, in fermentum metus elementum a. Suspendisse eu tellus sit amet
    > lectus accumsan dapibus a ut erat. Aliquam id rutrum eros. In in cursus lectus. Quisque cursus
    > molestie orci non dictum. Praesent aliquam erat sit amet felis varius, vitae congue odio scelerisque.

    **Hint**: для разрешения конфликтов рекомендуется использовать один из вышеуказанных графических клиентов.

11. Проверьте состояние репозитория при помощи команд `git status` и `git log`. История коммитов должна выглядеть приблизительно так:

    ```shell
      commit aaa9e366e1e15fb6bf7880551969c018cccb597f
      Merge: e5a3eda d2beb8a
      Date:   Mon Oct 17 22:52:33 2023 +0300
      Merge changes from merge-branch-02

      commit d2beb8a6a7948aca19e48867e2541ef4683612a3
      Date:   Mon Oct 17 22:47:48 2023 +0300
      Add second line of lorem ipsum

      commit e5a3eda66a15b3a0c59d8d25806a5d585f4d0d3d
      Date:   Mon Oct 17 22:36:17 2023 +0300
      Make changes using lorem ipsum
    ```

12. Сохраните изменения, выполненные в каждой из веток - `merge-branch-01`, `merge-branch-02`, `master`, в удалённом репозитории с одноимёнными названиями.

### Задача 6. Разрешение конфликтов. Операция `rebase`

1. Перейдите в локальный репозиторий **git-example**.
2. Убедитесь в том, что текущая ветка - `master`. Заберите изменения из удалённого репозитория при помощи команды `git pull`.
3. Создайте ветку `rebase-branch-01` от ветки `master`.
4. Находясь в рамках ветки `rebase-branch-01` создайте директорию **db** в корне и переместите внутрь файл _pandas.json_.
5. Откройте файл _pandas.json_ и добавьте в его конец следующую запись:

   ```js
    {
      "id": 11,
      "name": "Bubochka",
      "type": "giant panda"
    }
   ```

6. Создайте коммит с текущими изменениями и сохраните его в удалённой ветке `rebase-branch-01`.
7. Переключитесь на ветку `master`. Cоздайте директорию **db** в корне и переместите внутрь файл _pandas.json_.
8. Модифицируйте файл _pandas.json_ путём добавления в его конец следующей записи:

   ```js
    {
      "id": 11,
      "name": "Toporik",
      "type": "red panda"
    }
   ```

9. Зафиксируйте свои изменения коммитом в рамках ветки `master`. Сохраните свои изменения в удалённой ветке `master`.
10. Переключитесь на ветку `rebase-branch-01` и совершите `rebase` на `master`, разрешив конфликты в файле _pandas.json_ таким образом, чтобы запись **Bubochka** шла перед записью **Toporik**. Обратите внимание на поле **id**.

    **Hint**: для разрешения конфликтов рекомендуется использовать один из вышеуказанных графических клиентов.

11. Проверьте состояние репозитория при помощи команд `git status` и `git log`. История коммитов должна выглядеть приблизительно следующим образом:

    ```shell
     commit e10c09915cb6ab66b2391f878da3293eb8a6c992
     Date:   Mon Oct 17 22:22:17 2023 +0300
     Add panda Bubochka

     commit 77e36303a6177f499b7cd431212121b24c281a12
     Date:   Mon Oct 17 22:24:52 2023 +0300
     Add Toporik panda
    ```

12. Попробуйте сохранить свои изменения в удалённом репозитории \(ветка `rebase-branch-01`\) при помощи команды `git push`. Обратите внимание на ошибку, которая возникает при использовании команды без опций.
13. Используя специальные опции команды `git push`, сохраните изменения в удалённой ветке.
14. Используя веб-сервис проверьте историю коммитов в удалённой ветке `rebase-branch-01`.
15. Обратите особое внимание на состояние ветки `rebase-branch-01` в рамках текущей задачи и ветки `master` после заврешения `merge` операции в рамках задачи № 5.

### Задача 7. Изменение последнего коммита

1. Перейдите в локальный репозиторий **git-example**.
2. Убедитесь в том, что текущая ветка - `master`.
3. Создайте ветку `ammend-01` от ветки `master`.
4. В корне репозитория создайте файл с именем _lyrics.txt_. Добавьте в него следующее содержимое:

   > In ancient days, in an ancient world, the Sibyls sung their melodies
   > But the song is lost, and no one hear when Sibyls speak the words of gods
   > the world is deaf
   > Ancient Sibylla we will follow you...

5. Создайте коммит с текущими изменениями и сохраните его в удалённой ветке `ammend-01`.
6. На основании ветки `ammend-01` создайте ветку `ammend-02` и сохраните её в удалённом репозитории.
7. Оставаясь в ветке `ammend-02`, откройте файл _lyrics.txt_ и добавьте в конец следующие строки:

   > O' Hermes Trismegistos, Orpheus, Zarathustra, Pythagoras and Plato
   > Mediate the wisdom!
   > Philosophers eternal, make the spirit flying, rising to spheres harmonic
   > where Sibyls are still singing

8. Сохраните изменения в файле путём изменения текущего коммита. Для этого изучите возможности команды `git commit`. В рамках изменения текущего коммита внесите правки заодно и в имя коммита.
9. Сохраните свои изменения в удалённом репозитории в ветке `ammend-02`.

### Задача 8. Создание `pull`/`merge` request

1. Перейдите в локальный репозиторий **git-example**.
2. Убедитесь в том, что локальный и удалённый репозиторий находятся в состоянии, равном завершени задачи №6. В таком случае удалённый репозиторий содержит следующие ветки - `rebase-branch-01`, `master`, причём `rebase-branch-01` опережает `master` на 1 коммит.
3. С помощью графического веб-интерфейса создайте `pull`-request из ветки `rebase-branch-01` в ветку  `master`.
4. При создании `pull`-request'а обратите внимание на следующие поля:
   * Название `pull`-request'a. Оно должно быть осмысленным и кратко и чётко описывать все изменения, сделанные в рамках PR.
   * Описание `pull`-request'a. Более подробная информация об изменениях, важные моменты в реализации, зависимости, если имеются, особенности тестирования.
   * Кто будет выступать в качестве code reviewer'а.


### Тулинг

Для работы с репозиторием можно пользоваться любым клиентом, будь-то консоль или любой удобный для Вас GUI - [DesktopGitHub](https://desktop.github.com/), [Tortoise Git](https://tortoisegit.org/), [Source Tree](https://www.sourcetreeapp.com/), [GitKraken](https://www.gitkraken.com/), [GitFork](https://git-fork.com/), etc. Использование консоли лучше всего позволяет понять, что же на самом деле происходит при работе с системой контроля версий, однако графические приложения могут упростить и ускорить ряд операций. По желанию, Вы можете повторить часть задач с использование приложения. Также Вам может потребоваться блокнот. Я рекомендую использовать [Notepad++](https://notepad-plus-plus.org/downloads/)

## Дополнительные материалы

Дополнительную инфрмацию можно почитать [тут](https://github.com/git-guides) и вот [тут](https://www.atlassian.com/ru/git/glossary#commands).
