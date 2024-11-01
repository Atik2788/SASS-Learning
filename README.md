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

**************************
#### Variables
$heade-bgColor: #6d4b18;

// use variables
***
header{
     background-color: $heade-bgColor;
}

#### nesting
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

#### mixin
// use class and pass the paramiter.
***
@mixin para-style($size, $style){
    font-size: $size;
    text-align: $style;
    margin: 10px 0;
}

#about p{
    @include para-style(17px, left);
}

#education p{
    @include para-style(10px, justify);
}


#### extend
.btn{
    border: none;
    padding: 5px 10px;
    text-align: center;
    font-size: 1rem;
    cursor: pointer;
}

.btn-download{
    //use btn class use @extend and the name of btn class.
    ***

    @extend .btn;
    background-color: #3f8f9b;
    border-radius: 20px;
    color: white;
}
