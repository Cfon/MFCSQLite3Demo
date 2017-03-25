<H1>MFCSQLite3Demo</H1>

Example1.zip<br>
В данный момент реализовано:<br>
подключение к БД Chinook.db;<br>
просмотр данных в окне представления с прокруткой;<br>
выбор таблиц из меню;<br>
используется архитектура документ/вид.<br>

пс. база Chinook.db, файлы SQLite3 и обертка под MFC уже есть в архиве Example1.zip
проект создавался с испльзованием среды разработки Visual Studio 2012-2015.<br>

что такое Chinook? это база данных некого цифрового медиа хранилища<br>
см по ссылкам:<br>
https://chinookdatabase.codeplex.com/<br>
http://www.sqlitetutorial.net/sqlite-sample-database/<br>
https://blog.xojo.com/2016/04/13/the-chinook-sample-database/<br>

----------------------------------------------------------------------------
update1 (Example1.1.zip):<br>
страничный просмотр данных, юзал не сильно мудреный сиквел:<br>
SELECT * FROM table LIMIT 50 OFFSET n;<br>
навигация при помощи меню, кнопок на тулбаре, а также кнопок на вьюшке под таблицей с выборкой данных.<br>
 
