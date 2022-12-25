# Лабораторная работа 2

## Задание

Разработать и реализовать клиент-серверную информационную систему, реализующую механизм CRUD
Интерфейс системы представляет собой веб-страницу с лентой заметок, отсортированных в обратном хронологическом порядке и форму добавления новой заметки.

Возможности пользователей:
- добавление текстовых заметок в общую ленту
- реагирование на чужие заметки(лайки)

## Ход работы

### Пользовательский сценарий работы 
Пользователь  **page.php**, вводит любое текстовое сообщение. В случае корректного ввода данных, его сообщение появится в ленте в обратном хронологическом порядке. 
Пользователи могут ставить лайки на понравившиеся записи и комментировать их. Для этого необходимо ввести свой комментарий в поле под записью и нажать кнопку **Комментировать**.

###

###  API сервера и хореография

### Структура базы данных

Для хранения данных форума используется база данных MySQL.

База данных содержит 2 таблицы : `posts` и `comments`

 Таблица `posts`
| Название | Тип | NULL | Дополнительно | Описание |
| :------: | :------: | :------: | :------: | :------: |
| **id** | INT  | NO | AUTO_INCREMENT | Автоматический идентификатор поста |
| **time** | TEXT | NO | | Дата создания поста |
| **msg** | INT | NO | | Текст поста |
| **likes** | INT | NO | | Количество лайков |
| **dislikes** | INT | NO | | Количество дизлайков |

Таблица `comments`
| Название | Тип | NULL | Дополнительно | Описание |
| :------: | :------: | :------: | :------: | :------: |
| **id** | INT  | NO | AUTO_INCREMENT | Идентификатор комментария |
| **id_msg** | INT  | NO | | Идентификатор поста |
| **comm_txt** | TEXT | NO | | Текст комментария |
| **time** | DATETIME | NO | | Дата написания комментария |
