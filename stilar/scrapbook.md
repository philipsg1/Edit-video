# Stil: Scrapbook

**Kommando:** `redigera i Scrapbook-stil`, eller bara `Scrapbook`

Det här är ett kortformat för TikTok och Reels där en person pratar rakt in i kameran. Claude redigerar hela råfilmen på egen hand: klipper bort omtagningar och pauser, lägger på undertexter ord för ord och klistrar in lekfull "scrapbook"-grafik.

Stilen bygger på en exempelvideo som användaren beskrev. En råfilm på 2:24 blev ett färdigt klipp på 0:41. Referensvideon finns inte sparad, så detaljerna nedan är tolkningar av beskrivningen och bör justeras efter första testet.

---

## 1. Format
- Stående 9:16, 1080×1920 och 30 bilder per sekund.
- Standardlängd **max 45 sekunder**, om inget annat anges.
- Undertexter på **svenska**, om inget annat anges.

## 2. Klippning (det viktigaste)
- Transkribera hela råfilmen med tidsstämplar per ord.
- **Ta bort omtagningar.** När en mening sägs flera gånger behålls bara den sista hela versionen.
- Ta bort felsägningar, "eh", "öh" och pauser längre än ungefär 0,3 sekunder.
- Kapa bort det som inte för berättelsen framåt, så att resultatet håller sig under maxlängden.
- Räkna antalet omtagningar som togs bort. Siffran används i kvittot (avsnitt 5).

## 3. Undertexter
- Ett ord i taget lyser upp, i karaoke-stil. Hela frasen syns, och ordet som sägs just då markeras med färg eller lätt förstoring.
- Kort fras per rad, ungefär 3–5 ord, i nedre tredjedelen av bilden.
- Tjockt, lättläst typsnitt med kontur eller bakgrundsplatta.

## 4. Grafik ("scrapbook")
Grafiken byggs i kod (Pillow och ffmpeg) och dyker upp med en kort pop- eller studsanimation.
- **Lappar med tejp:** papperslappar med tejpbit i hörnet, med nyckelord eller rubriker.
- **Pratbubblor:** för kommentarer, skämt och reaktioner.
- **Polaroidbilder:** frysta bildrutor ur videon, eller bilder på produkter och saker som nämns, i vit polaroidram och lite snett placerade.
- **Filmremsa:** ett filmremsemotiv, till exempel som intro, kapitelavdelare eller ram runt en sekvens.
- Allt lutar några grader, som om det vore handplacerat.
- Har användaren laddat upp en logga eller angett varumärkesfärger, till exempel Saigon Food, används de.

## 5. Redigeringskvitto (avslutning)
- Under de sista 2–3 sekunderna visas ett **kvitto** som ser ut som ett kassakvitto och sammanfattar redigeringen, till exempel:
  ```
  REDIGERINGSKVITTO
  Råfilm ........... 2:24
  Färdig ........... 0:41
  Omtagningar bort .... 9
  Pauser bort ........ 37
  ```
- Kvittot rullar fram uppifrån, som när det skrivs ut.

## 6. Ljud
- Originalrösten är det viktigaste ljudet och ska vara tydlig, med normaliserad volym.
- Ljudeffekterna görs själva (syntetiseras i ffmpeg eller Python), såvida inte användaren laddar upp egna:
  - "pop" när lappar, bubblor och polaroider dyker upp
  - "swoosh" vid övergångar
  - kamerans slutarljud när en polaroid visas
  - kvittoskrivarens ljud vid kvittot
- Musik används bara om användaren laddar upp egen.

---

## Vad Claude behöver från användaren
1. **Råfilmen**, där personen pratar in i kameran. Uppladdningsgränsen i chatten är cirka 40 MB, så komprimera till 720p eller 1080p om filen är större.
2. Valfritt: längd, plattform, språk, stil (lekfull eller stilren), logga och färger.
3. Annars gäller standardinställningarna ovan, och Claude redigerar helt på egen hand.

## Arbetsgång
1. Transkribera med faster-whisper (svenska, tidsstämplar per ord). Ge ljudet som en numpy-array.
2. Hitta omtagningar och pauser och bygg en klipplista.
3. Klipp med ffmpeg.
4. Bygg undertexter som en ASS-fil med karaoke-taggar.
5. Rendera grafiken som PNG-bilder med Pillow och lägg på dem med ffmpeg overlay, med tid och animation.
6. Mixa in ljudeffekterna och lägg kvittot på slutet.
7. Exportera en mp4 med H.264 och AAC och skicka den till användaren. Fråga sedan efter feedback.
