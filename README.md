
<H1>MFCSQLite3Demo</H1>

<b>Example1.zip</b><br>

В данный момент реализовано:<br>
<ul>
<li>подключение к БД Chinook.db;</li>
<li>просмотр данных в окне представления с прокруткой;</li>
<li>выбор таблиц из меню;</li>
<li>используется архитектура документ/вид.</li>
</ul>

пс. база Chinook.db, файлы SQLite3 и обертка под MFC уже есть в архиве Example1.zip
проект создавался с испльзованием среды разработки Visual Studio 2012-2015.<br>

что такое <b>Chinook</b>? это база данных некого цифрового медиа хранилища<br>
см по ссылкам:<br>
https://chinookdatabase.codeplex.com/<br>
http://www.sqlitetutorial.net/sqlite-sample-database/<br>
https://blog.xojo.com/2016/04/13/the-chinook-sample-database/<br>

ссылка на саму обертку SQLite3 под MFC (автор <b>midnightEngineer</b>):<br>
https://www.codeproject.com/Articles/10060/SQLite-MFC-Wrapper<br>

----------------------------------------------------------------------------
update1 (<b>Example1.1.zip</b>) реализовано:<br>
<ul>
<li>страничный просмотр данных, юзал не сильно мудреный сиквел:</li>
SELECT * FROM table LIMIT 50 OFFSET n;<br>
<li>навигация при помощи меню, кнопок на тулбаре, а также кнопок на вьюшке под таблицей с выборкой данных.</li>
 </ul>

пс. если что-то будет удаляться из предыдущих версий примера, то это будет указано.

----------------------------------------------------------------------------
update2 (<b>Example1.2.zip</b>) реализовано:<br>
<ul>
<li>сортировка</li>
SELECT * FROM table ORDER BY field LIMIT 50 OFFSET n<br>
<li>выбор сортировки через комбо-список, расположенном на тулбаре</li>
 </ul>
