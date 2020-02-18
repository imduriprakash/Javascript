# Javascript
Javascript samples
This repo accompanies a series of code samples in Javasript/ JQuery.

## readvisiblecells.html
This sample javacript function read the visiable characters in given html table by skipping non visible characters, where table cell's background color and cell color are matching.
```
function rgb2hex(rgb) {
     if (  rgb.search("rgb") == -1 ) {
          return rgb;
     } else {
          rgb = rgb.match(/^rgba?\((\d+),\s*(\d+),\s*(\d+)(?:,\s*(\d+))?\)$/);
          function hex(x) {
               return ("0" + parseInt(x).toString(16)).slice(-2);
          }
          return "#" + hex(rgb[1]) + hex(rgb[2]) + hex(rgb[3]); 
     }
}
function myFunction() {
    var str ='';
    var table = document.getElementsByTagName("table");
    var rc = table[0].rows.length;
    for (var i = 0; i < rc; i++) {
    row = table[0].rows[i];
    var cc = row.cells.length;
	    for (var j = 0; j < cc; j++) {
	        col = row.cells[j];
	        bgcol = col.style.backgroundColor;
	        bghex = rgb2hex(bgcol);
	        //console.log(bghex);
	        cellcolor = col.style.color;
	        cellhex = rgb2hex(cellcolor);
	        console.log(cellhex);
	        if(bghex != cellhex)
	        {
	            str = str + col.innerHTML;
	        }
	    }  
	}
	alert(str);
}
```

