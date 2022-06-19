Тестовое задание


Задача:
Реализовать приложение, которое умеет показывать следующие страницы:

/ - главная страница (страница на которой будет выведена любая информация (текст и картинка)
/login — страница регистрации, ввода логина и пароля
/news - страница с новостями (любая однотипная информация полученная с API).
/profile - страница с выводом информации о выбранном пользователе (переход по нажатию на любого пользователя).
/frends - страница на которой будут отображаться данные всех юзеров пришедшие по API.
На сайте, в шапке реализовать функционал:

Слева: логотип;

Справа: Вход / Выход: (при нажатии на «Вход» - перекидывает на страницу (/login), «Выход» - происходит разлогинивание и переход на страницу (/);

На сайте, в боковом меню реализовать ссылки:

На главную (/);
Профиль (/profile) - отображается только при логине;
Друзья (/frends) - отображается только при логине;
Новости (/news);

Если пользователь кликает на страницу “профиля” или “друзья” и он не “авторизован” - перекидывать на страницу /login/.


Форма входа (/login) принимает “фейковые” данные:

username: Admin

password: 12345

Если введены другие данные, то показывается сообщения:

Имя пользователя или пароль введены не верно

Если введены корректные данные, то перебрасывать на страницу (/profile) — где отображать пользователя (id=1)

Информацию об авторизации пользователя можно хранить в localStorage (обычные поля user, password). Базу данных реализовать не нужно.

Все необходимое на ваш взгляд, прокинуть через Redux.

При клике по любому юзеру на странице (/frends), должен будет произойти переход на страницу (/profile) с отображением данных выбранного юзера, а также его постов.

Оформление (дизайн) — не важно. Сделайте, чтобы можно было комфортно смотреть пример в браузере и на мобильных устройствах.


Требования:
Для асинхронных запросов использовать redux-thunk, или любой другой подход.
Использовать редьюсеры и экшены, как того требует redux.
При переходе на страницу пока пока она грузиться (подгружает данные) — показывать прелоадер.
Пока запрос на логине «в процессе», блокировать повторные запросы (самый легкий способ, это блокировать нажатия кнопки входа + сделать disabled кнопку отправки формы). Разумеется, чтобы пользователю было понятнее, текст disabled кнопки можно сделать: «Проверяю…» либо прелоадер как на профиле/новостях.
В форме показывать ошибку + стандартную валидацию email (по типу инпута, либо по регулярному выражению).
Разместить проект на GitHub pages
https://www.c-sharpcorner.com/article/how-to-deploy-react-application-on-github-pages/


API:

https://jsonplaceholder.typicode.com/users — подгрузка всех юзеров;

https://jsonplaceholder.typicode.com/users/id — подгрузка конкретного юзера по id;

https://jsonplaceholder.typicode.com/posts -  подгрузка всех постов; (также используется для вывода новостей (поля title, body));

https://jsonplaceholder.typicode.com/posts?userId=id - подгрузка постов у конкретного юзера;