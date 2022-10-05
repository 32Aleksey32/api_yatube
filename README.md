# api_yatube - спринт №8 в Яндекс.Практикум
## Спринт 8 - CRUD для Yatube

CRUD (сокр. от англ. create, read, update, delete — «создать, прочесть, обновить, удалить») — акроним, обозначающий четыре базовые функции, используемые при работе с персистентными хранилищами данных:

- создание;
- чтение;
- редактирование;
- удаление.

### Перечень доступных эндпойнтов:
- api/v1/api-token-auth/ (POST): передаём логин и пароль, получаем токен.
- api/v1/posts/ (GET, POST): получаем список всех постов или создаём новый пост.
- api/v1/posts/{post_id}/ (GET, PUT, PATCH, DELETE): получаем, редактируем или удаляем пост по id.
- api/v1/groups/ (GET): получаем список всех групп.
- api/v1/groups/{group_id}/ (GET): получаем информацию о группе по id.
- api/v1/posts/{post_id}/comments/ (GET, POST): получаем список всех комментариев поста с id=post_id или создаём новый, указав id поста, который хотим прокомментировать.
- api/v1/posts/{post_id}/comments/{comment_id}/ (GET, PUT, PATCH, DELETE): получаем, редактируем или удаляем комментарий по id у поста с id=post_id.

### Настройка и запуск на компьютере
Клонируем проект:
```
https://github.com/32Aleksey32/api_yatube.git
```
Переходим в папку с проектом:
```
cd api_yatube
```
Устанавливаем виртуальное окружение:
```
python -m venv venv
```
Активируем виртуальное окружение:
```
source venv/Scripts/activate
```
Устанавливаем зависимости:
```
python -m pip install --upgrade pip
pip install -r requirements.txt
```
Применяем миграции:
```
python yatube/manage.py makemigrations
python yatube/manage.py migrate
```
Создаем супер пользователя:
```
python yatube/manage.py createsuperuser
```
Запускаем проект:
```
python yatube/manage.py runserver
```

После чего проект будет доступен по адресу http://127.0.0.1:8000/

Заходим в http://127.0.0.1:8000/admin и создаем посты, группы, комментарии. Тестировать и добавлять данные удобно после прохождения авторизации через Postman.
