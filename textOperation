class textOperation{
	
	function wp_strip_all_tags($string, $remove_breaks = false) { // чистит все теги 
		$string = preg_replace( '@<(script|style)[^>]*?>.*?</\\1>@si', '', $string );
		$string = strip_tags($string);

		if ( $remove_breaks )
			$string = preg_replace('/[\r\n\t ]+/', ' ', $string);

		return trim($string);
	}
	
	function cleanTextHtml($text){
	$search = array ("'<script[^>]*?>.*?</script>'si",  // Вырезается javascript 
					 "'<[\/\!]*?[^<>]*?>'si",           // Вырезаются html-тэги 
					 "'([\r\n])[\s]+'",                 // Вырезается пустое пространство 
					 "'&(quot|#34);'i",                 // Замещаются html-элементы 
					 "'&(amp|#38);'i", 
					 "'&(lt|#60);'i", 
					 "'&(gt|#62);'i", 
					 "'&(nbsp|#160);'i", 
					 "'&(iexcl|#161);'i", 
					 "'&(cent|#162);'i", 
					 "'&(pound|#163);'i", 
					 "'&(copy|#169);'i" 
	); 

	$replace = array ("", 
					  "", 
					  "\\1", 
					  "\"", 
					  "&", 
					  "<", 
					  ">", 
					  " ", 
					  chr(161), 
					  chr(162), 
					  chr(163), 
					  chr(169) 
	); 

	$text = preg_replace($search, $replace, $text); 	
	return $text;
	}
	
	function delsimbpl($text){
		$del_symbols = array(",", ".", ";", ":", "\"", "#", "\$", "%", "^",
                         "!", "@", "`", "~", "*", "-", "=", "+", "\\",
                         "|", "/", ">", "<", "(", ")", "&", "?", "?", "\t",
                         "\r", "\n", "{","}","[","]", "'", "“", "”", "•",
                         " как ", " для ", " что ", " или ", " это ", " этих ",
                         " всех ", " вас ", " они ", " оно ", " еще ", " когда ",
                         " где ", " эта ", " лишь ", " уже ", " вам ", " нет ",
                         " если ", " надо ", " все ", " так ", " его ", " чем ",
                         " при ", " даже ", " мне ", " есть ", " раз ", " два ", " в ", "не",
                         " 0 ", " 1 ", " 2 ", " 3 ", " 4 ", " 5 ", " 6 ", " 7 ", " 8 ", " 9 "
                         );
		$text = str_replace($del_symbols, ' ', $text);
		return $text;
	}
	
	function wordcount($text){
		$text = $this->clearnBadHtml($text);
		$text = $this->cleanTextHtml($text);
		$text = $this->delsimbpl($text);
		$array = explode(' ', $text);
		echo '<pre>';
		print_r($array);
		echo '</pre>';
		return count($array);
		$array = $this->RemoveEmpty($array);
		return count($array);
	}
	
	function clearnBadHtml($code){ // убрать noindex nofollow <!---->
		$res = preg_replace("|<noindex>(.*?)</noindex>|si",'',$code);
		$res = preg_replace("|<style>(.*?)</style>|si",'',$res);
		$res = preg_replace("|<script(.*?)>(.*?)</script>|si",'',$res);
		$res = preg_replace("|<link(.*?) />|si",'',$res);
		$res = preg_replace("|\n\n|si",'',$res);
		$res = preg_replace("|\r\r|si",'',$res);
		//$res = preg_replace("|<a(.*?)rel=(.*?)nofollow(.*?)</a>|si",'',$res); // не всегда срабатывает
		$res = preg_replace("|<!--(.*?)-->|si",'',$res);
		$res = preg_replace(array("<noindex>","</noindex>"),'',$res);
		return $res;
	}
	
	function RemoveEmpty($array)
	{
		$Result = array();
		foreach ($array as $key => $value) {
			if ($value != '')
				$Result[] = $value;
		}
		return $Result;
	}
}
