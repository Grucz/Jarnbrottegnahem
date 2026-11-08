# Järnbrotts egnahemsförenings webbplats

Statisk webbplats. Filerna ligger här i GitHub, och Netlify publicerar om
sidan automatiskt inom en minut varje gång något sparas här.

Ingen kod behöver byggas eller installeras. Allt som behövs för att ändra
sidan finns i filerna nedan, och de går att redigera direkt i webbläsaren
genom att klicka på pennikonen.

## Filerna

| Fil | Vad den är |
|---|---|
| `index.html` | Startsidan. Måste heta exakt så, annars hittar Netlify den inte |
| `jarnbrottsnytt.html` | Arkivet över Järnbrottsnytt, plus informationen om sponsring |
| `bli-medlem.html` | Avgifter, betalning och servisskadefonden |
| `handlingar.html` | Stadgar och de tre senaste årsmötesprotokollen |
| `grupper.html` | Facebook och Grannsamverkan |
| `historik.html` | Föreningens historia |
| `kontakt.html` | Styrelsen, revisorer och valberedning |
| `style.css` | Allt utseende för alla sidor. Ändras här, slår igenom överallt |
| `manifest.json` | Gör att sidan kan läggas på mobilens hemskärm |
| `bilder/` | Logotyp, foton, omslag och ikoner |
| `dokument/` | Alla pdf-filer |

## Återkommande uppgifter

**Lägga till en aktivitet i kalendariet.** Öppna `index.html` och leta efter
ordet KALENDARIUM. Där står en instruktion i klartext. Kort version: kopiera
ett helt block som börjar med `<li` och slutar med `</li>`, klistra in det och
byt datum och text. Gamla aktiviteter behöver inte tas bort, sidan döljer dem
själv dagen efter det datum som står i `data-slut`.

**Lägga till ett nytt Järnbrottsnytt.** Exportera numret till pdf från Keynote,
döp filen efter år och månad enligt mönstret `jarnbrottsnytt-2027-02.pdf` och
lägg den i mappen `dokument`. Gör en bild av förstasidan med samma namn fast
`.jpg`, och lägg den i `bilder`. Kopiera sedan ett helt block som börjar med
`<article class="nr">` i `jarnbrottsnytt.html` och byt ut filnamn och text.
Inget gammalt nummer ska tas bort, arkivet är poängen.

**Lägga till ett årsmötesprotokoll.** Föreningen publicerar de tre senaste.
När ett nytt läggs till ska alltså det äldsta tas bort, både länken i
`handlingar.html` och pdf-filen i `dokument`. Kontrollera innan uppladdning
att protokollet inte innehåller närvarolistor, röstlängder eller gatuadresser
till enskilda medlemmar.

**Byta styrelse efter årsmötet.** Namnen står i `kontakt.html`, både i listan
över vem man ringer och i listan över hela styrelsen.

## Att tänka på

Filnamn skrivs med små bokstäver och bindestreck, aldrig med mellanslag eller
å, ä och ö. De hamnar i webbadresser och strular annars.

Sidan har ingen service worker, vilket betyder att den inte sparas ner i
telefonen och inte kan skicka notiser. Det är ett medvetet val: en cachad
sida kan visa gammalt innehåll efter en uppdatering, och notiser hade krävt
en server och någon som skickar dem. Nyheter sprids i stället via föreningens
facebooksida.

Går något sönder: Netlify byter inte ut den publicerade sidan om ett bygge
misslyckas, och under Deploys går det att välja en tidigare publicering och
trycka Publish deploy för att återställa allt.

## Bilden på historiksidan

Det svartvita flygfotot i `historik.html` saknar uppgift om fotograf och
källa. Om den uppgiften kommer fram bör den skrivas in i bildtexten.
