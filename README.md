#### Git-хуки

Скрипты для обработки хуков лежат в каталоге .hooks.
##### 1) Клиентский git-хук, допускающий только сообщения в коммите определённого формата: [идентификатор задачи] Текст сообщения
За идентификатор в данном случае будем принимать номер задачи (допускаются только цифры).

Кастомизация хука commit-msg. В случае верного формата коммит будет выполнен, иначе выводится ошибка и коммит не проходит.

Пример работы для коммита неправильного формата:

<a href="https://ibb.co/kyPGQYc"><img src="https://i.ibb.co/rtXQ4ny/12.png" alt="12" border="0"></a>

Пример работы для коммита правильного формата:

<a href="https://ibb.co/9yqb0jk"><img src="https://i.ibb.co/1R9rNxt/3ver2.png" alt="3ver2" border="0"></a>
##### 2) Клиентский git-хук, форматирующий весь публикуемый код с использованием любого из case-инструментов (phpcbf)
Кастомизация хука pre-commit. Для демонстрации работы был создан контроллер TestController, в котором намеренно нарушено форматирование (поставлены лишние пробелы). При помощи инструмента phpcbf код был отформатирован насколько это возможно (см. https://github.com/sveta290700/lab8/commit/0d9ec0a0a4ddf1f00858f8b0869bcf2c33d0365a).

Пример выполнения форматирования см. в демонстрации работы хука 1), скриншот 1 (хук срабатывает перед выполнением коммита).

На скриншоте 2 демонстрации работы хука 1) можно заметить информацию о том, что ошибки были исправлены.
##### 3) Серверный git-хук, возвращающий “Hello world”-сообщение
Кастомизация хука post-update. Выполняется при пуше на git-сервер.

Пример работы:

<a href="https://ibb.co/b12prTQ"><img src="https://i.ibb.co/XX3mz1j/4.png" alt="4" border="0"></a>