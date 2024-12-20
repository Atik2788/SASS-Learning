# SASS-Learning
#### install "Live SASS Compailer"
#### Go to File > Preferences > Settings (or Code > Preferences > Settings on macOS).
#### Click on the Open Settings (JSON) icon in the top-right corner to edit the settings.json file.
"liveSassCompile.settings.formats": [
    {
        "format": "compresed",
        "extensionName": ".css",
        "savePath": "/dist",
        "savePathReplacementPairs": null
    }
],
<br />
<br />
### Variables
$heade-bgColor: #6d4b18;
<br />
// use variables
<br />
header{
     background-color: $heade-bgColor;
}<br />
<br />
<br />
### nesting
 nav{
    margin-top: 0;

    ul{
        list-style: none;
        padding: 10px 0;

        li{
            display: inline-block;
            margin: 0 15px;

            a{
                display: inline-block;
                color: white;
                text-decoration: none;
                padding: 10px;
                transition: .4s;
                border-radius: 5px;
             }
             
             a:hover{
                background-color: black;
             }
         }
     }
 }
 <br />
<br />
### mixin 
// use class and pass the paramiter. <br />
<br />
@mixin para-style($size, $style){ <br />
    font-size: $size; <br />
    text-align: $style; <br />
    margin: 10px 0; <br />
} <br />
 <br />
#about p{ <br />
    @include para-style(17px, left); <br />
} <br />
 <br />
#education p{ <br />
    @include para-style(10px, justify); <br />
} <br />
 <br />
 <br />
### extend <br />
.btn{ <br />
    border: none; <br />
    padding: 5px 10px; <br />
    text-align: center; <br />
    font-size: 1rem; <br />
    cursor: pointer; <br />
} <br />
 <br />
.btn-download{
    //use btn class use @extend and the name of btn class. <br />
    *** <br />
    @extend .btn; <br />
    background-color: #3f8f9b; <br />
    border-radius: 20px; <br />
    color: white; <br />
}<br />
<br />
<br />
### if else css
<br />
@mixin setFontSize($value){ <br />
    @if $value == small{ <br />
        font-size: 12px; <br />
    } <br />
    @else if $value == medium{ <br />
        font-size: 16px; <br />
    } <br />
    @else if $value == large { <br />
        font-size: 20px; <br />
    }
    @else{ <br />
        font-size: none; <br />
    } <br />
}<br />  
<br />
<br />

### loop in SASS @for
<br />
[class*="col-"]{ <br />
    float: left; <br />
    text-align: center; <br />
    background: #efeaeaa7; <br />
    margin: 5px; <br />
} <br />
 <br />
// 1 to 13 means it is stop before 13 <br />
// 1 through 13 means it is stop after 13 <br />
// @for $i from 1 to 13 <br />
// @for $i from 1 through 12 <br />
 <br />
@for $i from 1 through 12{ <br />
    .col-#{$i} {width: 100% / 12 * $i} <br />
} <br />
 <br />
 <br />

 ### map over items using @each
 <br/>
// First way <br/>
/* @each $color in red, green, blue, white { <br/>
  .#{$color}-text { <br/>
    color: $color; <br/>
  } <br/>
} */ <br/>
 <br/>
 <br/>
// Second way <br/>
$colors: ( <br/>
  color1: red, <br/>
  color2: green, <br/>
  color3: blue, <br/>
); 
 <br/>
@each $color in $colors { <br/>
  .#{$color}-text { <br/>
    color: $color; <br/>
  } <br/>
} <br/>