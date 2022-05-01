## Лабораторная работа по ТиМП № 2 Васина Александра
# Part 1
_1.Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com)._

_2.Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге._
```
mkdir lab02 && cd lab02
git init
git remote add origin git@github.com:vasinaa/lab02.git
git branch -m main
git pull origin main
```
_3.Создайте файл ```hello_world.cpp``` в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу ```Hello world ``` на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку  ``` using namespace std; ``` ._
```
hello_world.cpp <<EOF
#include <iostream>
using namepace std;
int main() { cout << " Hello World " << endl;}
EOF
```
_4.Добавьте этот файл в локальную копию репозитория._
```
git add hello_world.cpp
```
_5.Закоммитьте изменения с осмысленным сообщением._
```
git commit -m "Hello World first version"
```

_6.Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение  ``` Hello world from @name ``` , где @name имя пользователя._
 ```
 cat > hello_world.cpp <<EOF
> #include <iostream>
> #include <string>
> 
> int main() 
> {
>  std::string name; // creating the name
>  std::cin >> name; // enter name
>  std::cout << "Hello World from " << name << std::endl ; // print
> }
> EOF

 ```
_7.Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?_
``` git commit -m "hello_world version 2" ```

_8.Запуште изменения в удалёный репозиторий._
``` git push origin main ```
_9.Проверьте, что история коммитов доступна в удалёный репозитории._

# Part 2
_1.В локальной копии репозитория создайте локальную ветку  ``` patch1 ``` ._
```git checkout -b patch1 ```

_2.Внесите изменения в ветке ``` patch1``` по исправлению кода и избавления от ``` using namespace std;``` ._
```
cat > hello_world.cpp <<EOF
> #include <iostream>
> #include <string>
> 
> int main() 
> {
>  std::string name; // creating the name
>  std::cin >> name; // enter name
>  std::cout << "Hello World from " << name << std::endl ; // print
> }
> EOF
```


_3.**commit, push** локальную ветку в удалённый репозиторий.
```
git add hello_world.cpp
git commit -m " new version"
git push origin patch1
```

_4.Проверьте, что ветка ```patch1``` доступна в удалёный репозитории._
_5.Создайте pull-request ``` patch1 -> master```._
_6.В локальной копии в ветке  ```patch1``` добавьте в исходный код комментарии._
_7. **commit, push.**
```
git add hello_world.cpp
git commit -m "comments"
git push origin patch1
```
_8.Проверьте, что новые изменения есть в созданном на **шаге 5** pull-request_
_9.В удалённый репозитории выполните слияние PR ``` patch1 -> master``` и удалите ветку ``` patch1``` в удаленном репозитории._
_10.Локально выполните **pull**._
```
git pull origin main
git pull origin main
```
_11.С помощью команды ``` git log ``` просмотрите историю в локальной версии ветки ```master```._
```
git log
commit 3a7e5483adcde9beb393e008d74127031eb1dd6c (HEAD -> main, origin/patch1, patch1)
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 13:04:28 2022 +0300

    comments

commit 41f3ec5d9b926c66330eb9dd061a85a50c7e6106
commit 41f3ec5d9b926c66330eb9dd061a85a50c7e6106
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 12:52:53 2022 +0300

     new version

commit aa2412599044d1af233963876657c7c5ec5a5f9b (origin/main)
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 12:30:35 2022 +0300

    hello_world version 2

commit cf0bd55e5c85895e45f052d75d2f22bb6a80a576
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 12:24:46 2022 +0300

    Hello World first version

commit d1e59fc5c1c3bec22cb4ba12045d0556af4bcdbc
Author: vasinaa <99878647+vasinaa@users.noreply.github.com>
Date:   Sun May 1 12:15:43 2022 +0300

    Initial commit
...skipping...
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 12:52:53 2022 +0300

     new version

commit aa2412599044d1af233963876657c7c5ec5a5f9b (origin/main)
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 12:30:35 2022 +0300

    hello_world version 2

commit cf0bd55e5c85895e45f052d75d2f22bb6a80a576
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 12:24:46 2022 +0300

    Hello World first version

commit d1e59fc5c1c3bec22cb4ba12045d0556af4bcdbc
Author: vasinaa <99878647+vasinaa@users.noreply.github.com>
Date:   Sun May 1 12:15:43 2022 +0300

    Initial commit
...skipping...
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 12:52:53 2022 +0300

     new version

commit aa2412599044d1af233963876657c7c5ec5a5f9b (origin/main)
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 12:30:35 2022 +0300

    hello_world version 2

commit cf0bd55e5c85895e45f052d75d2f22bb6a80a576
Author: vasinaa <avasinaa15@yandex.ru>
Date:   Sun May 1 12:24:46 2022 +0300

    Hello World first version

commit d1e59fc5c1c3bec22cb4ba12045d0556af4bcdbc
Author: vasinaa <99878647+vasinaa@users.noreply.github.com>
Date:   Sun May 1 12:15:43 2022 +0300
Initial commit 
```

_12.Удалите локальную ветку ```patch1```._
``` git branch -d patch1```

# Part 3
_1.Создайте новую локальную ветку ```patch2```._
```git checkout -b patch2```
_2.Измените ``` code style``` с помощью утилиты ``` clag-format```. Например, используя опцию ``` -style=Mozilla```._

_3.commit, push, создайте pull-request ```patch2 -> master```._
```
git add hello_world.cpp
git commit -m "Mozilla codestyle"
git push origin patch2
```
_4.В ветке master в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык._
_5.Убедитесь, что в pull-request появились конфликтны._
_6.Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты._
```
git rebase main
git push --force origin patch2 
```

_7.Сделайте force push в ветку ```patch2```_
_8.Убедитель, что в pull-request пропали конфликтны._
_9.Вмержите pull-request ```patch2 -> master.```_

  
  
  
 

 
