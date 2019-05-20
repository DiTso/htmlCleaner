# htmlCleaner
Класс php для работы с текстом
Чистка всех тегов в коде;
удаление лишних символов и слов, которые не имели большого значения при дальнейшем анализе текста;
удаление участков кода, которые не принимают участия в индексации страницы и не влияют на выдачу в поисковых системах;
Класс для чистки html кода и работы с текстом
$obj = new textOperation;
$text = '	<ul class="sub-menu">
		<li id="menu-item-2662" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-2662"><a href="https://wp-admin.com.ua/uroki-frilansa/oblasti-frilansa/"><span>Области фриланса</span></a></li>
	</ul>
</li>
	<li id="menu-item-2671" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-2671"><a href="https://wp-admin.com.ua/uroki-frilansa/frilans-i-fultaym-sushhestvuyut-vmeste/"><span>Фриланс и фултайм существуют вместе</span></a></li>
	<li id="menu-item-2669" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-2669"><a href="https://wp-admin.com.ua/uroki-frilansa/test-smogu-li-stat-frilanserom/"><span>Тест смогу ли стать фрилансером</span></a></li>
	<li id="menu-item-2661" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-2661"><a href="https://wp-admin.com.ua/uroki-frilansa/mogu-li-ya-stat-frilanserom/"><span>Могу ли я стать фрилансером?</span></a></li>
</ul>';
echo $obj->wp_strip_all_tags($text);
