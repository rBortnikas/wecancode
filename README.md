```javascript
function test() {
  console.log("notice the blank line before this function?");
}
```


```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```



# Projekto eiga

Programavimo aplinka https://codesandbox.io/s/oqnz8n1pqz

* Map.js
* Form.js
* Index.html
* styles.css


###  1.&nbsp;&nbsp;&nbsp;index.html faile keisime mūsų puslapio išvaizdą
##### Pradėsime nuo puslapio aprašymo:

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>We can code beginner challenge</title>
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
</head>

<body>

</body>
</html>
```
***
### 2.&nbsp;&nbsp;&nbsp;Kuriame žemėlapį ir dedame jį į mūsų puslapį
##### 2.1. Pildome styles.css failą:

```css
#map {
	width: 100%;
	height: 300px;
}
```
##### 2.2. Kuriame pirmąją map.js funkciją. Ji užkraus žemėlapį į mūsų app’są:
```javascript
(function(root) {
 	///
-------------------------------------------------------------------------
 	// local variable for accessing created map.
 	var googleMap;
 	// initializing map
 	function initMap() {
 		console.log("map ready");
 		var myLatLng = { lat: 54.8898944, lng: 23.7871816 };
 		googleMap = new google.maps.Map(document.getElementById("map"), {
			zoom: 4,
			styles: [
		 		{
					featureType: "transit.station",
					stylers: [{ visibility: "off" }] // Turn off bus, train stations etc.
 				}
 			],
			disableDoubleClickZoom: true,
			streetViewControl: false,
			center: myLatLng
 		});
 	}
	// exposing to global
	root.initMap = initMap;
})(typeof self !== "undefined" ? self : window);
```
##### 2.3. Pastarųjų žingsnių darbo rezultatą “prijungiame” prie index.html dokumento:
```html
...
	<meta charset="utf-8" />
	<title>We can code beginner challenge</title>
	<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
	<link rel="stylesheet" href="css/styles.css" type="text/css" />
</head>
<body>
	<div id="map"></div>

	<script src="js/map.js"></script>

	<script src="https://maps.googleapis.com/maps/api/js?key=&callback=initMap"></script>
</body>
</html>
...
```

