<!DOCTYPE html>
<html>
<head>
<meta http-equiv="content-type" content="text/html; charset=UTF-8">
<meta name="robots" content="noindex, nofollow">
<meta name="googlebot" content="noindex, nofollow">

<style type="text/css">

</style>

<title></title>

<script type='text/javascript'>//<![CDATA[
window.onload=function()
{
	var test = document.getElementById('test');
  var but1 = document.getElementById('but');
  var ref = document.getElementById('butRefresh');
  
	var testValue;
	var rightAnswer;
  
  but1.onmousedown = myalert;
	ref.onmousedown = refresh;
  
	refresh();

  function refresh()
  {
    var formula = "p * V = m / M * R * T";
    var space = randomInteger(0, formula.length - 1);
    
    while(formula[space] < 'A' || formula[space] > 'z')
      space = randomInteger(0, formula.length - 1);

    rightAnswer = formula[space];
    formula = formula.substring(0, space) + "?" + formula.substring(space + 1);

    document.getElementById('formula').innerHTML = formula;
		but1.nextElementSibling.innerHTML = "";
		test.value = "";
  }

	function randomInteger(min, max) 
	{
    	var rand = min + Math.random() * (max + 1 - min);
    	rand = Math.floor(rand);
    	return rand;
 	}

	function myalert()
	{ 
		if(test.value == rightAnswer)
		{
			this.nextElementSibling.innerHTML = "СORRECT";
			this.nextElementSibling.style.color = "green";
		}
		else
		{
			this.nextElementSibling.innerHTML = "INСORRECT";
			this.nextElementSibling.style.color = "red";
		}
	}
}

</script>

</head>

<body>

  <meta name="viewport" content="width=device-width, user-scalable=yes">

  <p> <b id = "formula"></b> </p>

  <input type="text" id="test" />

  <input type="button" value="Проверить " id="but">

  <p>^введите ответ^</p>

  <input type="button" value="Ещё раз!" id="butRefresh">

</body>

</html>
