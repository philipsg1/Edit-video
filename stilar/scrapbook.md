# Stil: Scrapbook

**Kommando:** `redigera i Scrapbook-stil`, eller bara `Scrapbook`

Det här är ett kortformat för TikTok och Reels där en person pratar rakt in i kameran. Claude redigerar hela råfilmen på egen hand: klipper bort omtagningar och pauser, lägger på undertexter ord för ord och klistrar in grafik som ser handgjord ut. Det ska kännas som en anteckningsbok eller ett skrivbord med papperslappar, tejp, polaroider, klotter, stämplar och ett kvitto.

Referensvideon är från @rory.ridgers: 44,9 sekunder, 576×1024 pixlar, 24 bilder per sekund. Råfilmen var 2:24 och den färdiga videon 0:41.

---

## 1. Format och tempo
- Stående 9:16, slutexport i 1080×1920. Både 24 och 30 bilder per sekund fungerar.
- Standardlängd **max 45 sekunder**.
- Talet styr allt. Pauser och omtagningar klipps bort så att personen pratar utan avbrott.
- Det ska hända något grafiskt ungefär var 3:e–5:e sekund, men det får finnas lugna partier med bara personen och undertexter (som 17–21 s i referensen).

## 2. Färger och typsnitt
| Roll | Färg | Typsnitt (Google Fonts) |
|---|---|---|
| Papper och lappar | krämvitt `#F4F0E8` med lätt pappersstruktur och skugga | |
| Accent (kursiv, cirklar, handskrift, "bad") | korall/tegel `#E07A5F` | |
| Bakgrund vid "skärmlägen" | salviagrön skärmatta `#5E8C73` med ljusa rutlinjer | |
| Överstrykningspenna | gul `#F6C744` | |
| Text | nästan svart `#1E1E1E` | |
| "good"-märke | ljusgrön `#A8C7A0` | |
| Rubriker | | **Instrument Serif** eller DM Serif Display. Viktigaste ordet i kursiv korall. |
| Handskrift | | **Caveat** |
| Prompter, kvitto och filetiketter | | **Courier Prime** eller JetBrains Mono (skrivmaskin) |
| Undertexter | | **Poppins Bold** eller Inter ExtraBold |

## 3. Undertexter
- 1–3 ord åt gången, synkade ord för ord, i **gemener** precis som de sägs.
- Placering: centrerat, ungefär 70–72 % ner i bilden.
- Vanliga ord är vita med mjuk skugga.
- **Ordet som sägs just nu** får mörk text på en **gul överstrykningsruta** (`#F6C744`) bakom sig.
- **Varumärken och nyckelnamn** ("Claude", "Opus") får korallfärg i stället.

## 4. Grafiska byggstenar (scen för scen i referensen)
| Tid | Moment | Hur det ser ut |
|---|---|---|
| 0–5 s | **Rubriklapp** | Krämvit papperslapp tejpad överst och lite sned: "Claude *edited* this video." i serif, med *edited* i kursiv korall. Under står i handskrift "…and I haven't even watched it", och en korallfärgad understrykning ritas fram. |
| 5–8 s | **Skärmdumpar på skärmatta** | Bakgrunden byts till den gröna skärmattan. Skärmdumpar av inlägg från X/Twitter tejpas upp, staplade och snedställda. En korallfärgad cirkel ritas runt nyckeltexten, och "15M views" står i handskrift. |
| 8–14 s | **Tankebubbla** | En tankebubbla ovanför huvudet. Små klotter (stjärna, våg, YouTube-play, spiral, gnista) ritas fram ett i taget. När han säger "haven't been able to produce themselves" stryks allt över med rött klotter. |
| 14–17 s | **Klistermärken och polaroider** | Klotter-klistermärken runt personen: stjärna, YouTube-knapp, cirkel och spiral. Polaroidliknande skärmdumpar med @namn nålas upp i toppen. |
| 21 s | **Utzoomning** | Videobilden krymper och får en vit fotoram, och vi hamnar på skärmattan. |
| 22–26 s | **Råfilmen som foto och prompt** | Videon visas som ett foto med etiketten `IMG_7093.MOV · 2:24 · RAW · UNCUT`, och en filmremsa med bilder från filmen till vänster. En lapp överst visar prompten, som skrivs fram med blinkande markör ("go through it and fully edit it on your own."). Under står i handskrift "= full creative freedom" med understrykning. |
| 27–28 s | **Post-knapp** | En korallfärgad knapp "Post" som en muspekare klickar på. Den blir "Posted ✓". |
| 29 s | **Stämpel** | En sned röd stämpel "UNWATCHED", med småtexten "Quality control · by any human", slås ner över bilden. |
| 30–36 s | **Redigeringskvitto** | Ett kassakvitto glider ner från toppen (se avsnitt 5). En gul överstrykningspenna drar över rader, och en röd cirkel ritas runt "0". |
| 37–40 s | **Uppmaning** | Handskrivet "tell me here" med en pil ner mot kommentarerna. Därefter poppar märkena "good" (grön), "or" (liten vit cirkel) och "bad" (korall) in ett i taget. |

Gemensamt för all grafik:
- Allt är lite snett (±2–6°), har mjuk skugga och tejpbitar i hörnen.
- Element kommer in med en kort **pop- eller studsanimation** eller en glidning (0,15–0,3 s).
- Linjer, cirklar och understrykningar **ritas fram** så att de ser handritade ut.
- Grafiken ska aldrig täcka ansiktet. Lägg den ovanför huvudet eller vid sidorna.

## 5. Redigeringskvitto
Skrivs i skrivmaskinstypsnitt på vitt kvittopapper med tandad underkant:
```
        * EDIT RECEIPT *
     08 OKT 2026 · TIKTOK / IG
 --------------------------------
 RAW FOOTAGE               2:24
 FINAL CUT                 0:41
 TIME CUT                  1:44
 RETAKES CUT                  9
 SOUND FX                    38
 --------------------------------
 EDITOR                OPUS 5.5
 TAKES                        1
 FREEDOM                   FULL
 HUMAN EDITS                  0
       thank you, come again
       ||||||||||||||||||||
```
- Siffrorna hämtas från redigeringen: råfilmens längd, den färdiga längden, borttagen tid, antal borttagna omtagningar och antal ljudeffekter.
- Datum och plattform fylls i automatiskt.

## 6. Ljud
Bedömningen bygger på ett spektrogram av referensen. Kvittot i referensvideon anger 38 ljudeffekter.
- **Röst:** originalrösten, tydlig och normaliserad. Den är alltid huvudsaken.
- **Bakgrundsmusik:** en mjuk, låg ljudbädd, ungefär -25 dB under rösten. Den hörs tydligast från cirka 13 sekunder och framåt.
- **Ljudeffekter:** omkring 1 per sekund, korta och lågmälda. Syntetiseras själva om användaren inte laddar upp egna:
  - **pop** när lappar, märken och klistermärken dyker upp
  - **swoosh** vid scenbyten och när kvittot glider in
  - **pennljud eller "scribble"** när cirklar, understrykningar och klotter ritas
  - **tangentklick** när prompten skrivs fram
  - **musklick** på Post-knappen och ett **"ding"** vid "Posted ✓"
  - **stämpelduns** vid "UNWATCHED"
  - **kvittoskrivarljud** när kvittot glider ner
  - **tejpljud** när en lapp tejpas upp

## 7. Avslut
- Videon slutar efter uppmaningen ("good or bad"). TikToks egen avslutningsskärm (logga och @namn) läggs till av plattformen och ska **inte** redigeras in.

---

## Vad Claude behöver från användaren
1. **Råfilmen**, där personen pratar in i kameran. Gränsen i chatten är cirka 40 MB.
2. Valfritt: längd, språk på undertexterna (standard är talets språk), logga och färger, samt skärmdumpar eller bilder som ska visas som "inlägg" eller polaroider.
3. Annars redigerar Claude helt på egen hand och väljer själv vilka scenmoment från avsnitt 4 som passar innehållet. Alla moment behöver inte vara med i varje video. Kvittot och undertexterna är alltid med.

## Arbetsgång
1. Transkribera med faster-whisper (tidsstämplar per ord). Ge ljudet som en numpy-array.
2. Hitta omtagningar (upprepade meningar, behåll den sista hela) och pauser över 0,3 s, och bygg en klipplista. Räkna antalet borttagna omtagningar till kvittot.
3. Klipp med ffmpeg.
4. Bygg undertexter som en ASS-fil med gul överstrykning på det aktiva ordet.
5. Rendera grafiken som PNG-bilder eller bildsekvenser med Pillow (lappar, tejp, kvitto, stämpel, märken, klotter) och lägg på dem med ffmpeg overlay, med tid och animation.
6. Skapa ljudeffekterna och mixa dem med `amix`. Räkna dem till kvittot.
7. Exportera en mp4 med H.264 och AAC och skicka den. Fråga sedan efter feedback.
