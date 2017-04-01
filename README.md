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
проект создавался с использованием среды разработки Visual Studio 2012-2015.<br>

что такое <b>Chinook</b>? это база данных некого цифрового медиа хранилища 
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
SELECT * FROM table ORDER BY field LIMIT 50 OFFSET n;<br>
<li>выбор сортировки через комбо-список, расположенном на тулбаре.</li>
 </ul>

<p><i><b>обнаружен косяк!</b> замедление работы при сортировке больших данных, видимо запрос на получение всех данных даже с учетом лимита не эффективен и данные всеравно получаются все в память! 
буду пробовать решить через добавление ограничения запроса WHERE:</i><br>
SELECT * FROM table WHERE field = 'value' ORDER BY field LIMIT 50 OFFSET n;</p>

----------------------------------------------------------------------------
update3 (<b>Example2.zip</b>):
<ul>
<li>сделан рефакторинг кода;</li>
<li>исправлен косяк см выше.</li>
</ul>
<p><b>причина</b>: вывод данных непосредствено из запроса, что приводило к зависанию при большом числе записей в таблице. 
теперь данные выводятся во вьюшку не напрямую из запроса, а предварительно загружаясь в кэш.</p>

----------------------------------------------------------------------------
update4 (<b>Example2.1.zip</b>):
<ul>
<li>упорядочены поля;</li>
<li>убраны магические числа в полях;</li>
<li>исправлена сортировка в связи с новым форматом запросов.</li>
</ul>
<p>для этого юзал 11 запросов SELECT с LEFT JOIN вида:<br>
SELECT al.albumId, al.title, ar.name FROM albums al
		LEFT JOIN artists ar ON al.artistid = ar.artistid
		ORDER BY %d ASC LIMIT %d OFFSET %d</p>

----------------------------------------------------------------------------
update5 (<b>Example2.2.zip</b>):
<ul>
<li>реализовано отслеживание положения мыши для выбора элемента выводимых данных из таблицы;</li>
</ul>
<p>пока все! :D <br>
данный подход будет еще подвержен рефакторингу;<br>
для его реализации юзался революционый поход основанный на интуиции :D</p>

----------------------------------------------------------------------------
update6 (<b>Example2.3.zip</b>):
<ul>
<li>готовы два диалога Customer и Album</li>
</ul>
<p>пока они тока отображают данные без возможности сохранения и других необходимых операций.<br>
это все в будующем :)<br>
Кроме того в диалоге Album пока не реализовано отображение списка треков, тоже в будущем все будет :)<br>
Чтобы увидеть нужный диалог используйте клик по строке в данными, революционый подход распознает что вам надо! :D<br>
Изначальный вариант с 50 кнопками на вьшке потерпел фиаско и признан утопией! :D</p>

