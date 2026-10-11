# portfolio-task-CA


Sidan på webben:
https://portfoliochastask.netlify.app/


Reflektion: Portfolio

Från skiss till kod:
Min första reaktion på skissen var positivt och funderade på att lägga till svag grå färg på vissa element. Det för att tydliggöra vad vissa element är och dämpa den vita bakgrundsstyrkan för ögonen. Förespådde att listorna i About-sektionen skulle vara det mest utmanande av alla byggdelar. About-listan bedömde jag skulle behöva en hel del flexibilitet med flex. Pawans mobil-läge på 600px motsvarar mitt tablet-läge på mitt skrivbord. Skärmar kring 320px-läge är standarden för mobiler. Pawans layout-skiss skulle inte hålla strukturen utan istället riskera att elementen kolliderar eller överlappar varandra. 

Innan kodbygget behövdes en samling av färg-variablerna i :root och ett gäng förinställningar i filen base.css. Denna fil ska vara tillgänglig för alla kommande HTML-filer eftersom de använder gemensamma element egenskaper för att forma och färga exempelvis header och footer. 

Kodbygget startades enligt mobile-first metoden. Det var en ovana för min del då jag alltid har byggt mina hemprojekt med laptop-first som utgångspunkt. Det kändes som att byta plats på ratten i bilen men efter ett tag så växte jag in i det. 




Semantik:
I början av min bekantskap med HTML hade jag tolkat taggarna som ett beskrivningsinnehåll. Det hjälpte även att lokalisera var i koden jag befann mig och dessutom var kodstrukturen enklare att förstå. Jag hade ingen aning om att strukturella taggar hade syftet att vägleda besökare som tar hjälp av skärmläsaren för att inte missa viktigt innehåll. 

På varje sida i projekten finns header, navigation, main, article, section, footer, h1-h6, p och a samt button-element. Vanliga taggar som formar hemsidan i sin helhet. Längre in i arbetsuppgiften behövde jag byta ut en button mot en <input type=checkbox> på header för att ändra på färgtema på sidan. När det var dags att testa sidans navigation via tab-knappen, blev input-knappen aldrig markerad som de andra interaktiva element. Det tog ett tag att förstå att jag behövde lägga till ett attribut tabindex="0" på label som är kopplat ihop med input, för att ställa tillbaka den i flödet vid tangentbordsnavigation.

Under byggprocessen var jag inte i behov av div särskilt mycket. På projektsidan använde jag en del div-element för att skapa några kort. Kortens textinnehåll höll sig innanför h2 och p, och var tillgängligt för skärmläsarna medan det visuella sköttes av div-elementet.   

Annat som jag behöver lyfta fram är listorna på aboutsidan. Det är ett details-element som används för att visa och dölja extra information och ett interaktiv komponent. Den strukturen godkändes inte av markup validation service under bygget eftersom div var ogiltigt innanför summary i details, utan fick ersättas med span som är ett inline-element. 




Layout:
Projektet utgick enligt mobile-first och många HTML-taggar var block-element, vilket innebär att elementen tar full bredd och gör så att elementen hamnar strax under varandra. Ju bredare skärmstorlek desto fler element kunde placeras på rad med hjälp av display: flex för att efterlikna skissen. 

På projektsidan används grid för att placera korten efter grid-rutmönstret och göra dem responsiva. Grid är effektivt i responsiv design för att fylla önskade ytor med funktionen repeat(auto-fit, minmax()). Flex kan också fylla tomma ytor men när antalet är udda följer mönstret inte det jag är ute efter. Min bedömning är att flex är utmärkt för ett parent-element som styr sina child-element i en riktning. Däremot är grid bättre för mer komplexa rutmönster åt två riktningar, horisontellt och vertikalt.

Detta projekt hade tre brytpunkter för mobil-läge, surfplatta-läge och bärbar dator-läge och inga extra brytpunkter alls. Den responsiva designen använde inte media queries särskilt mycket. Kan bero på att CSS-funktionen clamp() gjorde ett bra jobb med font-size, gap, width, padding och margin, för att kontrollera storlekarna utifrån skärmstorleken redan där. Det blev mindre behov av media queries.




Tillgänglihet:
Jag har försökt underlätta för alla som besöker sidan och väljer att titta in i källkoden. 

Sidan är responsiv och anpassar sig efter skärmstorlekar. Projektets brytpunkter är för mobilläge (425px), surfplatta (768px) och datorskärm (1024px).

Huvudlayouten behåller en liknande struktur när besökaren väljer att zooma in upp till 500%. 

Jag använder alltid måttenheten rem för att definiera storlekar på exempelvis text, margin, gap, padding och width. 1rem motsvarar standardstorleken för roten 16px.

Personer som använder skärmläsare ska kunna uppfatta innehållet. Jag använder en hel del aria-label i exempelvis listor och länkar, alt-texter på bilder och rätt semantiska taggar för passande innehåll.

Jag har följt skissens färgval men har behövt ändra lite i deras styrka. Vissa färgnyanser passade inte ihop. Jag tog hjälp av en färgkontrast-webbplats för att uppnå nivå AA, vilket är ett krav inom WCAG. Det förbättrade färgkontrasten för bättre visuell tydlighet och läsbarhet. 

Den som väljer att navigera med tangentbordets tabb-knapp möts av en tydlig fokusmarkering (outline) på varje interaktivt element. 

För den som vill dämpa ljusstyrkan ordentligt finns det möjlighet att trycka mån-knappen högst upp till höger i headern. Det är ett skräddarsytt label-element som beter sig som en knapp och känner av om den är tryckt för att ändra färgtema.

På varje sida finns det animerade element. Om besökaren har animationseffekter inställda på [AV] på sin dator, kommer hen inte att bli påverkad av animationen. Detta eftersom jag har lagt till @media (prefers-reduced-motion: reduce).

Styrkor och brister
Det har varit underhållande, intressant och lärorikt. Jag uppskattar en genomtänkt semantisk struktur, behagliga färgval och kontrast samt anpassade komponenter utifrån skärmstorlekar. 

Något mindre bra är att HTML-kodstrukturen blir mycket och kan leda till mycket scrollande för att hitta rätt innehåll samt en hel del upprepning av samma komponenter.

När det gäller CSS kan det bli tufft om klasser inte har tydliga namn. Det gäller att ge sig tid att fundera noggrant över klassdeklarationer. 




AI-vertyg:
Vid sidan om har jag haft god hjälp av AI som har förklarat för mig när jag har fastnat. Särskilt vid uppbyggnaden av details och summary-elementen på Aboutsidan och färgtemaväxlingen på sidorna och gett mig grundläggande kunskap inom animation. 

Till detta projekt använde jag mig av Google Gemini som stöd och jag valde bort ChatGPT. Gemini förstod mina beskrivningar bättre och gav mig fler alternativa vägar till lösningar. ChatGPT var kortfattat och vägledde mig oftast ingenstans. Gemini var mer engagerat i utvecklingsprocessen.

Jag använder AI för att få en förklaring av hur något används. Om AI visar en kodstruktur väljer jag att skriva koden i editorn istället för att kopiera och klistra in. Jag vill få förståelse för den kod jag använder och kunna dela med mig till andra intresserade. 

Det återstår att testa andra AI-verktyg gällande kodning. 