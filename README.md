
## Функционал

- Регистрация пользователя с валидацией (логин — латиница и цифры, ≥6 символов; пароль ≥8).
- Авторизация с информативными сообщениями об ошибках.
- Личный кабинет: история заявок + отзывы (после смены статуса администратором).
- Оформление заявки: вид транспорта, дата начала, способ оплаты — через выпадающие списки.
- Панель администратора (логин `Admin26` / пароль `Demo20`) с фильтрами, поиском,
  сортировкой и постраничной навигацией.
- Слайдер с 4 изображениями, авто-смена каждые 3 секунды, стрелки вперёд/назад.
- Мобильная адаптация под 390×844, микроанимации.

ИЗМЕНИТЬ ТЕКСТ

## Запуск

```bash
pip install -r requirements.txt

# создать БД demo123 в PostgreSQL (user: postgres / pass: postgres)
# или временно переключиться на SQLite в vodit_rf/settings.py

python manage.py migrate

python manage.py shell
>>> from django.contrib.auth.models import User
>>> User.objects.create_superuser('Admin26', 'admin@vodit.rf', 'Demo20')
>>> exit()

python manage.py runserver
```

## Структура

- `vodit_rf/` — настройки проекта
- `main/` — модели (Profile, Application, Review), формы, представления, URL'ы
- `main/templates/main/` — шаблоны Bootstrap
- `static/css/app.css` — стили, анимации, мобильная адаптация

ИЗМЕНИТЬ ТЕКСТ