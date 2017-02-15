# Коллаж фотографий на jQuery и Css

![alt text](https://pp.vk.me/c639317/v639317978/a869/kxWE4ysEd3w.jpg)

Установив стили на нужный блок отредактируйте скрипт под свои нужды. 
Так же скрипт обробатывает изображения с ссылкой:
```
<a href="#"><img ></a>
```

Блок в котором находятся все изображения.
```
var imgs = $('section img');
```

Сам скрипт
```
<script>
var imgs = $('section img'), obj;
$.each(imgs, function(i, v){
	var img = new Image();
	img.src = v.src;
	img.onload = function(){
		w = Math.round(img.width * 200 / img.height);
		w = (w > img.width ? img.width : w);
		h = Math.round(w * (img.height / img.width) + 40);
		obj = v.parentNode;
		(obj.tagName == 'A' ? obj : v).style = 'flex-grow: 1; ' + (obj.tagName == 'A' ? 'padding:5px;' : '') + 'width: ' + w + 'px; height: ' + h + 'px';
	}
})
</script>
```
