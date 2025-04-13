# Social Network API

## Описание
API для социальной сети с возможностью создания постов, подписки на других пользователей и взаимодействия с контентом.

## Установка
1. Клонируйте репозиторий
2. Создайте виртуальное окружение: `python -m venv venv`
3. Активируйте окружение: `source venv/bin/activate` (Linux/Mac) или `venv\Scripts\activate` (Windows)
4. Установите зависимости: `pip install -r requirements.txt`
5. Примените миграции: `python manage.py migrate`
6. Запустите сервер: `python manage.py runserver`

## Примеры запросов

### Получение подписок

1. GET /api/follow/
2. Authorization: Bearer <your_token>


### Создание подписки


POST /api/follow/
Authorization: Bearer <your_token>
Content-Type: application/json

{
"following": "username_to_follow"
}


### Установка
Для работы с JWT токенами:
1. Установите библиотеку: `pip install djangorestframework-simplejwt`
2. Добавьте в `urls.py`:
```python
from rest_framework_simplejwt.views import TokenObtainPairView, TokenRefreshView

urlpatterns = [
    path('api/token/', TokenObtainPairView.as_view()),
    path('api/token/refresh/', TokenRefreshView.as_view()),
]

