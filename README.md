## Краткое писание
**Simple wiki markup** – простой php скрипт преобразования wiki разметки в html код. Часть разметки взята из wikimedia, часть придумана (возможно просто забыл где видел). Присутствуют bb-codes.

## Возможности
==Заголовки== где == это h2, === это h3, и т. д. Если количество заголовков > 2 тогда будет генерироваться блок содержания (с якорями), стиль которого можно настроить. Блок содержания будет вставлен до текста.

Ссылки: 
* [[https:// site.zone/|текст ссылки]] => &lt;a href=&quot;https:// site.zone/&quot;&gt;текст ссылки&lt;/a&gt;
* [[https:// site.zone/]] => &lt;a href=&quot;https:// site.zone/&quot;&gt;https:// site.zone/&lt;/a&gt;

[code lang="язык"]код[/code] заменяется на &lt;pre class='brush: &quot;язык&quot;'&gt;код&lt;/pre&gt;
При использовании SyntaxHighlighter будет подсветка синтаксиса :)

Генерация todo листа: {{(.\*?)|(.\*?)}} где в первой скобке название анкора, во второй текст todo.
В конец текста будет добавлен блок со списком (div с классом указанным в m_sListTodo, элементы содержания в списке (ol, li))

\n\nТЕКСТ\n будет обернут в p тег, класс стиля можно настроить

Маркированные списки (ul):
* \* первый уровень
	* \*\* второй уровень
		* \*\*\* и т.д.

Нумерованные списки (ol):
1. \# первый уровень
	1. \#\# второй уровень
		1. \#\#\# и т.д.

bb-codes: b, i, u, d, left, center, right, sub, sup, big, small

((текст)) будет заменен на (&lt;small&gt;текст&lt;/small&gt;)

""текст"" будет заменен на &lt;u&gt;текст&lt;/u&gt;

''текст'' будет заменен на &lt;i&gt;текст&lt;/i&gt;

\#\#текст\#\# будет заменен на &lt;b&gt;текст&lt;/b&gt;

---- преобразуется в &lt;hr/&gt;

## Использование
	require_once('simple_wiki_markup.php');
	$sSampleText = file_get_contents("sample.txt");
	$html = swm::markup($sSampleText);
	echo $html;
  
## Лицензия
**MIT**

## Автор
Buturlin Vitaliy (Byurrer), email: byurrer@mail.ru
