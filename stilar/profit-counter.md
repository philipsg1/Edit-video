# Stil: Profit Counter

**Kommando:** `redigera i Profit Counter-stil`, eller bara `Profit Counter`

Det här är ett kortformat för TikTok, Reels och Shorts där någon öppnar Pokémon-kortpaket. En räknare på skärmen visar hela tiden om öppningen har gått med vinst eller förlust. Varje kort som dras får ett eget prismärke, och värdet läggs till på räknaren.

Stilen bygger på en referensvideo från @rare.holos. Videon är 41 sekunder lång, 576×1024 pixlar och har 30 bilder per sekund.

---

## 1. Format och tempo
- Stående 9:16, slutexport i 1080×1920 och 30 bilder per sekund.
- Längd 30–60 sekunder. Klipp bort alla pauser och all tystnad, så att det alltid händer något.
- Hela videon är en enda kontinuerlig berättelse: krok → kostnad → öppning → stor träff → slutreaktion.
- Mycket snabba kortbyten. Varje vanligt kort visas i ungefär 0,5–1 sekund.

## 2. Struktur (tidslinje från referensen)
| Tid | Del | Innehåll |
|---|---|---|
| 0–3 s | **Krok** | POV-ruta överst, till exempel *"POV: DU SER LÖSA SHINY TREASURE PACKS – NU ÄR DET DAGS ATT DRA BUBBLAN!"* Kortet han jagar visas som en inklistrad bild med prislapp. |
| 3–5 s | **Kostnad** | Stor text i mitten: *"DAGENS KOSTNAD:"* i gult och *"-597 SEK"* i rött eller rosa. En snabb inzoomning eller rörelseoskärpa när han viftar med paketen. |
| 5–8 s | **Målet** | Bild på kortet han jagar, med marknadspris: *"5 000 SEK"* och *"PSA 10: 8 500 SEK"* i grönt. |
| 8 s till slutet | **Öppning** | **PROFIT COUNTER** syns i övre vänstra hörnet från och med nu, ända till slutet. |
| Stora träffar | **Reaktion** | Klipp till ansiktet, och räknaren hoppar till exempel från -561 till -361. |
| Sista 5 s | **Avslut** | Personen pratar in i kameran (*"Inget dåligt, vi tar den, hej!"*). Räknaren står kvar på slutvärdet. |

## 3. Profit Counter (huvudelementet)
- **Placering:** övre vänstra hörnet, ungefär 5 % in från vänster och 5 % ner från toppen.
- **Rad 1:** `PROFIT COUNTER:` i gult (#FFE600) med svart kontur.
- **Rad 2:** `-597 SEK` i vitt eller ljusrosa med ett **rött, rosa eller magenta sken** (glow) när räknaren är negativ. När den blir positiv byts skenet till grönt.
- **Startvärde:** minus den totala kostnaden för paketen.
- **Vid varje kort:** räknaren ökar med kortets värde och uppdateras precis när prismärket syns.
- **Stora träffar (≥ 100 SEK):** siffran **räknar snabbt uppåt** under ungefär 0,3–0,5 sekunder i stället för att hoppa direkt, och ett **kassaapparatljud ("ka-ching")** spelas.

## 4. Prismärken per kort
- Grön text (#3CFF3C) med svart kontur, till exempel `2 SEK`, `180 SEK`, `200 SEK`.
- Placeras precis under eller bredvid kortet, i nedre halvan av bilden.
- Kommer in med en kort **pop- eller studsanimation** (skala 0 → 110 % → 100 % under ungefär 0,15 s) och syns lika länge som kortet.
- Kortet som jagas visas med två rader: `5 000 SEK` och `PSA 10: 8 500 SEK`.

## 5. Undertexter (talet)
- **Typsnitt:** tjockt kondenserat serietypsnitt med bara versaler, som **Bangers** (gratis på Google Fonts). Alternativ är Komika Axis eller Anton.
- **Visning:** 2–3 ord åt gången, synkat ord för ord.
- **Färg:** vit text med tjock svart kontur. **Ett nyckelord per fras är gult** (#FFE600), till exempel *"**JAKTEN** TAR SLUT"*, *"**BUBBLE** MEW JAG"* eller *"INGET **DÅLIG**"*.
- **Placering:** ungefär 75–80 % ner i bilden, centrerat och ovanför TikToks gränssnitt.
- Skriv engelska och slangord som de uttalas i stilen ("LAST PACK MAGIC", "SHISHARDEN").

## 6. Ljud
Analysen bygger på ett spektrogram av referensljudet.
- **Röst:** originalljudet, högt och tydligt. Det får aldrig drunkna.
- **Bakgrundsmusik:** svag och konstant ljudbädd under hela videon, ungefär -25 till -30 dB under rösten.
- **Kassaapparatljud ("ka-ching"):** vid varje stor träff, när räknaren hoppar ≥ 100 SEK. Det syntes tydligt i referensen vid 12,6 s, 19,3 s, 34,5 s och 35,8 s.
- **Svischljud eller kort "swipe"-ljud:** vid varje snabbt kortbyte och vid hopp mellan klipp.
- **Effektljud:** när *"DAGENS KOSTNAD"* visas, till exempel ett "fail"-ljud eller ett dramatiskt slag.
- **Pop-ljud:** kan läggas på när prismärken dyker upp.

## 7. Bildeffekter
- Snabb inzoomning eller rörelseoskärpa vid kroken och vid stora träffar.
- Lätt digital inzoomning (ungefär 105–115 %) på närbilder av kort, så att kortet fyller bilden.
- Inga övergångar mellan klippen. Använd bara raka klipp (hard cuts).

---

## Vad Claude behöver från användaren varje gång
1. **Den oredigerade videon.**
2. **Kostnaden** för det som öppnas, till exempel 597 SEK. Annars frågar Claude.
3. **Kortens värden** om du vill ha exakta priser. Annars identifierar Claude korten från bilden och uppskattar priser, och de uppskattningarna bör kontrolleras.
4. Valfritt: **vilket kort som jagas** och dess pris, plus texten till POV-kroken.

## Teknisk pipeline (plan)
1. Transkribera med faster-whisper (svenska, tidsstämplar per ord). Kör `pip install faster-whisper` och ge ljudet som en numpy-array.
2. Klipp bort tystnad och pauser.
3. Bygg undertexter som en ASS-fil med Bangers, 2–3 ord per rad och gult nyckelord.
4. Lägg överlägg för räknare, prismärken och kostnadsruta med ASS eller Pillow-genererade PNG-sekvenser.
5. Mixa ljudeffekter med ffmpeg-filtret `amix` vid de tidpunkter där priserna visas.
6. Exportera i 1080×1920 med H.264 och AAC.
