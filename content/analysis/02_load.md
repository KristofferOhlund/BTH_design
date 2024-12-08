---
Title: Load
Description: Loadingtime report page
Template: report
Hidden: true
---

# Page Loading Time

Denna rapport handlar om att undersöka olika webbplatsers &quot;hastighet&quot; - vilket kommer delas upp i olika grupper. Grupperna är följande: 
* Page Load Time: Tiden det tar för sidan att ladda och bli fullt interaktiv
* Time to first byte: Tiden det tar för server att svara på en request från användarens webbläsare
* First contentful paint: Tiden det tar för webbplatsens första innehåll att visas på skärmen, till exempel bilder
* Largest contentful paint: Tiden det tar för webbplatsens största innehåll att visas på skärmen
* First input delay: Tiden det tar för en användare att kunna interagera med webbplatsen efter att den blivit fullt laddad

## Urval
Rapporten kommer att fortsätta undersöka webbplatsens som togs upp i [Colors](%base_url%?analysis/01_colors) {.blue-link}

## Metod
För denna undersökning har jag använt verktyget [PageSpeed Insights](https://pagespeed.web.dev/) {.blue-link} vilket låter dig hänvisa till en URL och där sedan diverse analyser körs, se ovan för de mätvärden rapporten kommer inkludera.

Till undersökningen används även Devtools Inspect och följande värden kommer att mätas i omgångar om tre. 

* MB Transfered - mängden data som överförts från server, inkluderar hela webbsidans innehåll
* DOMContentLoaded - När HTML dockumentet laddats och parsats till ett DOM-träd, bilder och externa resurser inkluderas inte. (sidan blir då användbar)
* Load - När allting laddats, DOM-träd har parsats samt bilder och eventuella javascript är laddade.

## Resultat

### 1. [instant-gaming.com](https://www.instant-gaming.com/en/) {.blue-link} {.blue-link}

![Instant Gaming](%assets_url%/img/instant-gaming.png)

<div class="table-container">
    <table>
        <thead>
            <tr>
                <th>Kategori</th>
                <th>Värde</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>MB Transferred</td>
                <td>6.5 MB</td>
            </tr>
            <tr>
                <td>DOMContentLoaded</td>
                <td>392.6 ms</td>
            </tr>
            <tr>
                <td>Load</td>
                <td>896.6 ms</td>
            </tr>
            <tr>
                <td>Requests</td>
                <td>135</td>
            </tr>
        </tbody>
    </table>
</div>

Den största tidsboven enligt ![PageSpeed](https://pagespeed.web.dev) är antal Javascript som ska parsas, compileras och executas, en optimering av dessa skulle ge en tidsbesparing på 2.4sekunder.

### 2. [hastens.com](https://hastens.com/se/) {.blue-link} {.blue-link}

![Hästens sängar](%assets_url%/img/hästens.png)

<div class="table-container">
    <table>
        <thead>
            <tr>
                <th>Kategori</th>
                <th>Värde</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>MB Transferred</td>
                <td>7.73 MB</td>
            </tr>
            <tr>
                <td>DOMContentLoaded</td>
                <td>629 ms</td>
            </tr>
            <tr>
                <td>Load</td>
                <td>1.315 s</td>
            </tr>
            <tr>
                <td>Requests</td>
                <td>95</td>
            </tr>
        </tbody>
    </table>
</div>

Den största tidsboven enligt ![PageSpeed](https://pagespeed.web.dev) är antal Javascript som ska parsas, compileras och executas, en optimering av dessa skulle ge en tidsbesparing på 3.7sekunder.


### 3. [Hemnet](https://hemnet.se/) {.blue-link} {.blue-link}

![Hemnet](%assets_url%/img/hemnet.png)

<div class="table-container">
    <table>
        <thead>
            <tr>
                <th>Kategori</th>
                <th>Värde</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>MB Transferred</td>
                <td>6.03 MB</td>
            </tr>
            <tr>
                <td>DOMContentLoaded</td>
                <td>379 ms</td>
            </tr>
            <tr>
                <td>Load</td>
                <td>0.908 s</td>
            </tr>
            <tr>
                <td>Requests</td>
                <td>121</td>
            </tr>
        </tbody>
    </table>
</div>

Den största tidsboven enligt ![PageSpeed](https://pagespeed.web.dev) är antal Javascript som ska parsas, compileras och executas, en optimering av dessa skulle ge en tidsbesparing på 2.6sekunder.


## Analys

<iframe class="excel" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vREO_mICcY6PM2EtLrW-NUADC0p7A3dKGUSju9I5ZX_MOWqyJYxadLn_mkLOsBlipb_rnq2aM193wg8/pubhtml?widget=true&amp;headers=false"></iframe>

De vanligaste förbättringsåtgärderna enligt ![PageSpeed](https://pagespeed.web.dev) är:
1. Largest Contentful Paint
2. Reduce Javascript execution time
3. Minimize main thread work

Webbplatserna med bäst resultat är i rangordning nedan. Resultatet baseras på antalet requests samt de presenterade mätvärdena.

1. Instant-gaming.com
2. Hemnet.se
3. Hästens.com

Det var svårt att mäta den absoluta laddningstiden eftersom rubriken &quot;Finish&quot; som visas när DevTools Inspection används, inte var fast, utan tickade på trots att webbsidan till synes var färdigladdad och redo för interaktion. Därför har jag baserat den totala laddningstiden på Load - som ger en indikation på när webbplatsen blir interaktiv, och där stack hastens.com ut för att vara något långsammare. Det var en ytterst liten, men ändå märkbar delay på när bilderna laddats in - något som också kan bero på de större bilderna som laddas jämfört med övriga webbplatser i urvalet.
Samtliga webbplatser upplevs som snabba och gränsen för en snabb webbplats anser jag är de som har en "Load" under en sekund.Millisekunder är så pass snabbt så om det är 500 eller 700ms är knappt märkbart. 

## Övrigt

Undersökning och rapport är gjord av Kristoffer Öhlund, Akronym kroh24.