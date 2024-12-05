---
Title: Notes
Description: My notes
Hidden: true
---

## Färger och Assosciationer
* Röd - stimulerar adredatlin och blodtryck, ökar mänslik metabolism. Spännande dramatiskt färg, tar fram passion. 
* Orange - aktiv färg som sticker ut, skapar energi och bidrar till lycka, kreativitet. Används ofta vid viktiga föremål, livvästar, vägskyltar, vägkoner m.m
* Gul - aktiv, lycka, glad
* Grön - lugnande färg, symboliserar fräschet, hopp, tillväxt, lättare för ögonen än röd, gul och orange. Representetar rikedom, stabilitet, utbildning.
Blå - symboliserar öppenhet, intelligens och tro och har en lugnande effekt. Kan även symbolisera otur och problem, tänk på blues music. Kan även symboliserar med lugn och frid, tänk himmel och vatten. 
* Lila - historiskt sätt kopplats till kunglighet och makt. Det ger effekt från det stimulerande röda och den lugnande effekten från blå. Tänk vin, blommor, juveler. 
* Vit - Kan knytas till renhet, perfektion, ljus och renhet. Tänk bröllopsklänningar ex.
* Svart - Kan kopplas ihop med död och ondska, men också makt, elegans och styrka. 

### Varma färger

Röd till gul, orange, rosa, brun, vinröd / lila isch. representerar solen och eld, energi. Får element att poppa.

Kallar färger är färger från grön till blå, varianeter av violet. Kalla färger är lungnande och kan minska 'tension'.

### Färgscheman
* monochromatic (monokromatiskt) - Enfärgad, nyanser av samma färg
* analogous (analogt) - Närliggande färger på färghjulet
* complementary (komplement) - motsatta färger på färghjulet 
* split complemtentary - en färg och de två färgerna bredvid dess motsatta färg på färghjulet 
* triadic (triadiskt) - tre färger, jämt fördelade på färghjulet. Dela hjulet i tre delar och väljer färger från en del.
* tetradic - fyra färger, organiserade i två par av motsatta färger på färghjulet 
* achromatic - toner av svart, vit och grå.


## Färgmodeller
### CMYK - Cyan Magenta Yellow blacK (patroner för skrivare ex)
Vad är det? CMYK är en subtraktiv färgmodell som används för tryck och fysiska medier (tidningar, visitkort etc). Den arbetar med färgpigment i fyra grundfärger: Cyan (blågrön), Magenta (rosa), Gul (Yellow) och Svart (Key/Black).
* Istället för att addera ljus så subtraherar den ljus från vitt papper. Varje färg absorberar (subtraherar) en del av ljuset som träffar det vita pappret och det reflekterande ljuset är den färg vi ser. 
* Genom att kombinera CMYK kan man få nästan alla färger


### RGB - Red Green Blue
RGB är en additiv färgmodell som används för att skapa färger genom att blanda ljus i tre grundfärger: Röd (Red), Grön (Green) och Blå (Blue) och används på skärmar som datorskärmar, mobilskärmar och tvskärmar. Detta eftersom dessa enheter skapar färg med ljus. De är från början svarta och sedan adderas RGB ljus för att skapa olika färger.

* Varje färg skapas genom att kombinera olika mängder av rött, grönt och blått ljus.
* När alla tre grundfärger kombineras med maximal intensitet, får vi vitt ljus.
* Om ingen färg används (0% av rött, grönt och blått), blir det svart.


### Kontrast
Skillnad mellan färger. För att skapa lättlästa sidorna måste textens färg skilja sig mot bakgrundens färg på så sätt att texten sticker ut. Detta kallas för kontrast.

### Gradienter
Färger som går från en färg till en annan, kan skapa liv, men använd försiktigt för att inte ge huvudvärk. Tänk solnedgång.

### Hexadecimal 
RGB 0-255 (red, green blue) / RGBA (red, green, blue, alpha=genomskinlighet)
Aplha anges som tal mellan 0 och 1. Där 0.0 är ingen transparens och 1.0 är full transparens. 
Varje färg har 0-255 nivåer av röd, grön och blå. 
256 * 256 * 256 är ca 16 miljoner olika färger.
Hexadecimal baseras på multipler av sexton och har sex siffror.
* A - 10
* B - 11
* C - 12
* D - 13
* E - 14
* F - 15

### Programvaror
* [Paletton](https://paletton.com/#uid=1000u0kllllaFw0g0qFqFg0w0aF) 
* [Colormind.io](http://colormind.io/template/material-dashboard/)
* [Adobe Color](https://color.adobe.com/create/color-wheel)
* [Colour Contrast Check](https://webaim.org/resources/contrastchecker/)


### BILDER

    img, embed, object, video {
        max-width: 100%;
    }

Avänt ovan css för att alltid sätta bilder och liknande till 100% width av dess parent container.

    <picture>
        <source media="(min-width: 668px)" srcset="sheep.jpg, sheep@2x.jpg 2x">
        <source media="(min-width: 376px)" srcset="sheep-small-landscape.jpg">
        <img src="sheep-small-portrait.jpg" class="max-width" alt="sheep">
    </picture>

För att få olika bilder att laddas vid olika storlek av skärmar kan vi använda picture elementet.
source media är en media query, första exemplet säger om skärmen är minst 668px bred, ladda sheep.jpg, är det en retina skärm så ladda sheep@2x.jpg. Detta kan även ske med små skärmar men hög pixeldensitet, typ moderna telefoner, ihpone etc. Så srcset säger att ladda sheep.jpg om skärmen är minst 668px, eller ladda sheepp@2x om pixeldensiteten är dubbel (avslutande 2x).
Om skärmen är minst 376px men mindre än 668px så ladda srcset=sheep-small-landscape
Om skärmen är ännu mindre så laddas img src taggen

Om vi använder Bilder i vår markdown och vill lägga till en klass kan vi använda {<.class>} som tredje argument.
    ![Image Title](%assets_url%/image.png) {.small}


### CImage
I pico kan vi använda {%asset_url} för att skapa en sökväg till en bild, %asset_url% är standard enligt Pico och vi förväntas där ha assets som bilder osv. Om vi därför i vår markdown fil pekar på en bild genom att använda

    ![sample](%assets_url/folder/<bild.jpg>%)

så kommer bilden visas som förväntat, men vill vi kunna visa olika bilder vid olika skärmstorlekar behöver vi ha olika storleket på varje bild. Man behöver då tex via ett bild redigeringsprogram skapat varianter av samma bild.
Ett sätt att byta bild är då att använda ett picture element och använda srcset som du sätter olika bilder beroende på ex skärmens storlek.

    <picture>
        <source media="(min-width: 668px)" srcset="sheep.jpg, sheep@2x.jpg 2x">
        <source media="(min-width: 376px)" srcset="sheep-small-landscape.jpg">
        <img src="sheep-small-portrait.jpg" class="max-width" alt="sheep">
    </picture>

Om vi istället använder

    !|[sample](image/folder/<bild.jp>)

så har vi via vår .htacess gjort en rewrite fil som gör att vi istället använder CImage som redigeringsprogram och vilket då även möjliggör olika argument.

    <picture>
        <source media="(min-width: 668px)" srcset="image/sheep.jpg">
        <source media="(min-width: 376px)" srcset="image/sheep.jpg?w=667">
        <img src="image/sheep.jpg?w=375" alt="sheep">
    </picture>

se ?w=667 ovan, som sätter width på bilden till 667 pixlar.

### Tillgänglighet
Det är viktigt att ha alt attribut på bilder, då en synskadad som använder internet ändå kan få information om vad för slags bild som visas, genom att webbläsaren läser alt attributet.
Ett tips för att kunna kontrollera alla bilder om det har attributet är att använda css psuedo classen :not

    img:not([alt]) {
        outline: 4px red dashed !important;
    }

Ovan kollar alla img element och lägger på pseudo classen :not som tar ett attribut som argument. 
Här anges alt som attribut, sidan kollar då vilka img element som inte har alt attribut, och i så fall lägger på en outline. Det blir nu enkelt att se vilka bilder man glömt alt på.

### Page Speed
Page load time: The time it takes for a webpage to load and become fully interactive.
Server response time: The time it takes for a server to respond to a request from a user’s browser.
Core web vitals: A set of metrics that measure the performance of a webpage, including largest contentful paint (LCP), first input delay (FID), and cumulative layout shift (CLS).

Time to first byte (TTFB): The time it takes for a server to respond to a request from a user’s browser.
First contentful paint (FCP): The time it takes for the first content to be painted on the screen.
Largest contentful paint (LCP): The time it takes for the largest content element to be painted on the screen.
First input delay (FID): The time it takes for a user to interact with a webpage after it has loaded.