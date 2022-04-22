# lab02
## Part I
1) создаём директорию 

mkdir lab02

cd lab02

инициализируем git и подключаем гитхаб

git init

git remote add origin <ссылка на репозиторий>

2) создаём README.md

touch README.md

добавляем его в репозиторий

git add README.md

оставляем коммит

git commit -m"added REDAME.md"

пушим на гитхаб

git push --force origin master

3) Создаём файл 

touch hello_world.cpp

cat > hello_world. cpp <<EOF
                             
#inclde <iostream>

using namespace std;

int main()

{

  cout<<"hello world!";       

}

4) добавить файл в копию репозитория

git add hello_world.cpp

5) ещё раз закоммитить

git commit -m"added hello_world.cpp"

6)изменить код

edit hello.world.cpp

i - начало работы

:wq - конец

7) закоммитить программу

git commit -a -m"updated hello_world.cpp" -a позволяет обновлять файлы во время коммита

8) запушите изменения в удалённый репозиторий

git push --force origin master  --force чтобы наверняка

9) история коммитов

git log

## Part II

1) создать локальную ветку patch1

git checkout -b patch1

2) избавляемся от namespace

edit hello_world.cpp

3) commit

4) коммит пуш

 git commit -m"I fixed hello_world.cpp"
 
 git push --force origin patch1
 
5) pull-request 

делается на сайте

6) Добавить комментарии

edit hello_world.cpp

7) коммит пуш

как обычно (см. 4 шаг)

8)проверка

проверка прошла успешно

9)слияние веток

git checkout master

git merge patch1

git push --force origin master

10) git pull origin master

11) история веток:

git log

12) удаление ветки patch1

git push origin --delete patch1

## Part III

1) patch2

git checkout -b patch2

2) новый шрифт

sudo apt-get install clang-format

clang-format -i -style=Mozilla hello_world.cpp

git commit -a -m "New style hello_world.cpp"

3) создаем pull-request как обычно

4) изменение файла
5) конфликт

Чтобы появился конфликт, нужно изменить файл сначала в одной ветке, сменить её,
а затем снова изменить файл.

git checkout patch2

git rebase master видим конфликты

6) Чтобы от них избавиться, нужно отредактировать файл hello_world.cpp

rebase --continue объединяем изменения

7) Пуш

git push --force origin patch2

8) конфликты пропали

9) вдавливаем patch2 в master

git merge patch2

вторник 5-7
пятница 9
