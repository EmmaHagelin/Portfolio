# Portfolio – Emma Hagelin 

**Publicerad sida:** https://emmahagelin.github.io/portfolio/ 

## Reflektion 

### Från skiss till kod 
*Hur gick du tillväga? Vad var svårt att översätta till HTML och CSS, och hur löste du det?*
Jag började med att analysera skissen: fem sidor med gemensam header och footer, färger och typsnitt. Jag skrev ned allt i ett dokument som jag hade uppe hela tiden. Sedan skrev jag ned all HTML, därefter base.css med det gemensamma och sist stylade jag en sida i taget. Avstånd mätte jag i Figma genom att hålla ned Alt och hovra och jag räknade om px till rem. 

Det svåraste var att skissen inte var konsekvent. En rubrik hette både Technologies och Tech Stack, telefonnumret fanns bara på mobil och avståndet under hela headern varierade. Jag valde en version överallt, eftersom konsekvens gör sidan lättare att använda.

Hamburgermenyn löste jag utan JavaScript med <details> och <summary>. Gradienten i texten gjorde jag med background-clip: text och gradientramen runt bilden med padding och en gradient som bakgrund på .hero-image. Logotypen gjorde jag som text med mitt namn istället för en bild. 

 ### Semantik 
*Vilka element valde du för sidans delar, och varför? Var landar du i en div?* 
Jag använde header, nav, main, section och footer för sidans delar. Logotypen är en länk och inte en h1, eftersom varje sida har en egen h1. På About följer rubrikerna ordningen h1, h2, h3 trots att About me och Work Experience ser lika stora ut. Nivån handlar om struktur, storleken styrs med CSS.

Menyn, ikonerna, jobben och teknikerna ligger i ul så att en skärmläsare kan säga hur många objekt det finns. Projektkorten är <article> eftersom de är fristående innehåll, medan jobben är li i en uppräkning. Datum skrev jag med <time>, div använde jag bara där inget semantiska element passade, till exempel .project-grid, som bara finns för layoutens skull.

### Layout 
*Var använde du Flexbox respektive Grid, och vad avgjorde valet? Hur gjorde du sidan responsiv, och varför lade du brytpunkterna där?* 
Flexbox använde jag när innehållet går i en riktning: headern, menyerna, korten och .hero, som är en kolumn på mobil och en rad i desktop. Grid använde jag när layouten går i två riktningar, i .tech-grid, .project-grid och .timeline-item. Med grid-template-areas kunde jag ändra About-sidans desktoplayout utan att röra HTML:en.

Två flex-knep var användbara. Body som flex-kolumn och main { flex: 1} håller footern längst ned, och margin-top: auto trycker ned länkarna till botten av korten.
Jag arbetade mobile först och lade till regler för större skärmar med @media (min-width: 900). Brytpunkterna 600px och 900px valde jag genom att dra i fönstret och se var layouten slutade fungera, till exempel när tre projektkort blev för smala. En lärdom var att regler som hamnade utanför media queryn gjorde att desktoplayouten syntes på mobil. 

### Tillgänglighet 
*Vad har du gjort, hur testade du, vad visade testet och vad återstår?* 
Porträttet har en beskrivande alt-text och Tech Stack-ikonerna har teknikens namn. Dekorativa bilder och ikoner i länkar har tom alt=””.
Den grå färgen i footern och den gröna på etiketterna klarade inte av WCAG AA, så jag gjorde dem mörkare. 
Sidan fungerar med tangentbord. :focus-visible har en fokusfärg som klarar 3:1, och menyn öppnas med Enter. Jag använde aria-current=”page”, aria-label på logotypen och dold text med .visually-hidden i projektlänkarna, till exempel “live preview of …” Externa länkar öppnas i ny flik. Sidan har en lang=”en” och emojin är dold med en aria-hidden.
Jag testade med W3C:s validator, tangentbordet, Lighthouse, WebAIM contrast checker och DevTools. I Lighthouse fick jag 94, 96, 99, 96, 95 i den ordningen. Jag körde Narrator i Windows lite snabbt och jag hörde det mesta. Den läste till exempel upp att hamburgarknappen var ihopfälld. Det som återstår är att Tech Stack-ikonerna saknar synlig text.

### Användbarhet 
*Vilka UX/UI-principer känner du igen i designen? Vad hade du gjort annorlunda, och varför?* 
Pawans design följer flera principer för god användbarhet. Den är konsekvent, eftersom samma header och footer finns på alla sidor. Den har en tydlig visuell hierarki, med stora rubriker och grå undertext. Det finns gott om luft, och innehållets bredd är begränsad, vilket gör texten lättare att läsa.
Rubrik och undertext står nära varandra med större avstånd till innehållet, så man ser vad som hör ihop. Logotypen leder hem, och hamburgarikonen är ett känt mönster för en meny. 
Själv hade jag valt ett högre kontrast, synliga namn på teknik-ikonerna och samma innehåll på mobil och desktop.

### Styrkor och brister 
*Vad blev bra, och vad skulle du bygga om med mer tid?*
En styrka är att färgerna ligger i variabler, så när jag ändrade gradienten uppdaterades hela sidan. Uppdelningen i base.css och en fil per sida gör koden lätt att hitta i och menyn är tillgänglig utan JavaScript.

Den största bristen är att headern finns i fem filer, två gånger i varje. När jag uppdaterade den följde fel med, till exempel en fel CSS-länk och aria-current på Home på alla sidor. Med mer tid hade jag hittat ett sätt att dela kod mellan sidorna, lagt in riktiga skärmdumpar, designat en egen logotyp och testat med skärmläsare. 

 ### AI-verktyg 
*Till vad använde du AI, och vad ändrade du i det som genererades?* 
Jag använde AI till hjälp med att förklara vissa delar och vad jag skulle göra här näst trots att jag för det mesta skrev själv. Jag bad om hjälp när jag fastnade eller när jag inte kunde hitta felet i min kod. 
Jag följde inte alltid förslagen. Några gånger föreslog AI en <div> och då ändrade jag den och gav elementet en egen klass. 
När jag bad om hjälp bad jag AI beskriva varför och hur den gjorde som den gjorde med hur resultatet skulle bli. Jag bad den inte skriva koden åt mig om det inte var så att jag inte förstod vad den menar. 
