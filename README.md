# webmis3

https://drive.google.com/file/d/1sxlMWc7j1JflbETeRK-dtQxB6KOq7cWz/view?usp=sharing

##Часть 3

SQL
1) Получить список юзернеймов пользователей SELECT username FROM users;

2) Получить кол-во отправленных сообщений каждым пользователем SELECT username, COUNT(*) AS "number of sent messages" FROM messages JOIN users ON messages.from = users.id GROUP BY username;

3)  Получить пользователя с самым большим кол-вом полученных сообщений и само количество SELECT username, COUNT() AS "number of received messages" FROM messages JOIN users ON messages.to = users.id GROUP BY username ORDER BY COUNT() DESC LIMIT 1;

4) Получить среднее кол-во сообщений, отправленное каждым пользователем SELECT username, AVG(cnt) AS "average number of sent messages" FROM ( SELECT messages.from, COUNT(*) AS cnt FROM messages GROUP BY messages.from ) AS message_count JOIN users ON message_count.from = users.id GROUP BY username;


