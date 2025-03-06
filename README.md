# SecretSanta

## Описание

Secret Santa App - это Flutter-приложение, предназначенное для организации и проведения игры "Тайный Санта" среди сотрудников предприятия. Приложение позволяет упростить процесс жеребьевки, обмена информацией об участниках и управления проведенными играми.

## Функциональность

Приложение включает в себя следующие основные функции:

*   **Аутентификация пользователей:**
    *   Регистрация новых сотрудников.
    *   Вход в систему с использованием логина и пароля.
    *   Хеширование паролей для обеспечения безопасности.
    *   Разграничение прав доступа (администратор/организатор/участник).

*   **Управление сотрудниками (только для администраторов):**
    *   Просмотр списка всех сотрудников.
    *   Добавление новых сотрудников.
    *   Редактирование информации о сотрудниках (ФИО, должность, отдел, пожелания и т.д.).
    *   Удаление сотрудников.
    *   Поиск сотрудников по различным критериям.

*   **Управление играми "Тайный Санта":**

    *   **Для организаторов:**
        *   Создание новых игр с указанием даты начала и окончания.
        *   Редактирование информации об играх, находящихся в статусе "подготовка".
        *   Удаление игр, находящихся в статусе "подготовка".
        *   Рассылка приглашений сотрудникам для участия в игре.
    *   **Для администраторов:**
        *   Просмотр списка всех проведенных игр.
        *   Просмотр деталей каждой игры (список участников, результаты жеребьевки).
        *   Удаление игр (включая завершенные).

*   **Участие в игре (для участников и организаторов):**
    *   Просмотр информации о себе (анкета с пожеланиями).
    *   Заполнение анкеты с информацией о своих предпочтениях.
    *   Просмотр информации о своем подопечном (после проведения жеребьевки).

*   **Жеребьевка (только для организаторов):**
    *   Автоматическое распределение участников по парам "даритель-получатель" после закрытия регистрации на игру.
    *   Исключение возможности назначения самого себя в качестве получателя.
    *   Добавление и удаление участников игры.

*   **Рассылка уведомлений:**
    *   Автоматическая рассылка уведомлений, связанных с играми:
        *   Приглашение к участию в игре (организатором).
        *   Объявление результатов жеребьевки (организатором).
        *   Напоминания о приближающейся дате дарения (система).

*   **Отчетность (только для администраторов):**
    *   Формирование отчетов о проведенных играх.
    *   Просмотр статистики по играм.

## Требования к составу выполняемых функций (технические)

*   Авторизация сотрудников с хешированием паролей.
*   Разграничение прав доступа (администратор, организатор, участник).
*   Создание, чтение, обновление и удаление данных сотрудников и игр.
*   Поиск сотрудников по различным критериям.
*   Обновление и сохранение данных в базу данных (локальную или удаленную.....).
*   Работа с таблицами данных (только для администратора).
*   Формирование и просмотр отчётов (только для администратора).
*   Рассылка уведомлений, связанных с играми (организатором и системой).
*   Возможность добавления новых игр и управления ими (организатором).

## Входные данные:

*   **Для сотрудников:**
    *   Логин (уникальный идентификатор).
    *   Пароль.
    *   ФИО.
    *   Должность.
    *   ID отдела.
    *   Любимый цвет.
    *   Любимый фрукт.
    *   Любимый стиль одежды.
    *   Размер одежды.

*   **Для игр "Тайный Санта":**
    *   Дата начала игры.
    *   Дата окончания игры.

## Требования к организации выходных данных:

*   **Игровой интерфейс:**
    *   Для участников: отображение информации о своём подопечном (только после жеребьевки).
    *   Для организаторов: интерфейс для управления игрой (рассылка приглашений, запуск жеребьевки).
    *   Для администраторов: общая информация об игре, список участников, возможность управления.
*   **Списки участников:**
    *   Список сотрудников (только для администраторов).
    *   Список участников конкретной игры (для администраторов и организаторов).
*   **Анкеты участников:**
    *   Подробная информация о сотруднике (ФИО, должность, пожелания и т.д.).
    *   Доступна для просмотра администраторам, организаторам и самому сотруднику.
    *   Анкеты подопечных доступны дарителям после жеребьевки.
*   **Список проведённых игр:**
    *   Отображение списка завершенных и активных игр.
    *   Доступен для просмотра администраторам и организаторам.

## Технологии:

*   **Flutter:** Фреймворк для разработки кроссплатформенных мобильных приложений.
*   **Dart:** Объектно-ориентированный язык программирования, разработанный Google и используемый для создания приложений Flutter.
*   **База данных (локальная или удаленная):**
    *   **SQLite:** Для хранения данных непосредственно на устройстве пользователя.
    *   **MySQL:** Для хранения данных на сервере и обеспечения доступа к ним с разных устройств.  Необходимы для больших команд, обмена данными между устройствами и предоставления веб-интерфейса.
*   **Аутентификация и авторизация:**
    *   **shared_preferences:** Для хранения и кэширования данных пользователя.
    *   **crypto:** Для хеширования паролей в базе данных.
*   **Навигация:**
    *   **go_router:** Пакет для навигации и управления URL-адресами в приложении.
*   **Работа с датой и временем:**
    *   **intl:** Пакет для форматирования и локализации дат и времени.
*   **Уведомления (Ведётся разработка.... Работаю с этим впервые):**
    *   **Firebase Cloud Messaging (FCM):** Для отправки push-уведомлений на устройства пользователей.

## Структура проекта

* Изображение 1:
  
* ![Fl1](https://github.com/FinistFin/SicretSanta/blob/main/%D0%A1%D0%B0%D0%BD%D1%82%D0%B01.png)

* Изображение 2:
  
* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/%D0%A1%D0%B0%D0%BD%D1%82%D0%B02.png)

* Диаграмма 1:

* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/%D0%94%D0%B8%D0%B0%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B01.png)

* Диаграмма 2(основная):

* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/%D0%A1%D1%85%D0%B5%D0%BC%D0%B01.png)

* Диаграмма 3(дополнительная):

* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/%D0%A1%D1%85%D0%B5%D0%BC%D0%B02.png)

* Диаграмма 4(С информацие в бд мне нужна помощь, так как я не знаю полной организации компании, стоит ли указывать у сотрудников их отделы и тд?):

* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/%D0%91%D0%B0%D0%B7%D0%B0%D0%94%D0%B0%D0%BD%D0%BD%D1%8B%D1%85.png)

* Код модели Пользователи часть 1:

* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/User1.png)

* Код модели Пользователи часть 2:

* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/User2.png)

* Код модели Пользователи часть 3:

* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/User3.png)

* Код модели Игра часть 1:

* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/Game1.png)

* Код модели Игра часть 2:

* ![Fl2](https://github.com/FinistFin/SicretSanta/blob/main/Game2.png)

