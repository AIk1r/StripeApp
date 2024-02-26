# StripeApp
StripeApi
Команды для запуска: cd .\main_app\   python manage.py runserver
В проекте включен дебаг режим, ибо я не решил как лучше будет для тестирования его.
Таблица уже готова и в ней присутствуют 3 вещи. 

Реализовано: 
Django Модель Item с полями (name, description, price) 
API с двумя методами:
GET /buy/{id}, c помощью которого можно получить Stripe Session Id для оплаты выбранного Item. При выполнении этого метода c бэкенда с помощью python библиотеки stripe должен выполняться запрос stripe.checkout.Session.create(...) и полученный session.id выдаваться в результате запроса
GET /item/{id}, c помощью которого можно получить простейшую HTML страницу, на которой будет информация о выбранном Item и кнопка Buy. По нажатию на кнопку Buy должен происходить запрос на /buy/{id}, получение session_id и далее  с помощью JS библиотеки Stripe происходить редирект на Checkout форму stripe.redirectToCheckout(sessionId=session_id)

Бонусные задачи: 
Запуск используя Docker
Использование environment variables
Просмотр Django Моделей в Django Admin панели
