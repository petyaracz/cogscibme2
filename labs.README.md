# Kutatócsoport- (labor-) oldalak (`_labs/` mappa)

Ez a mappa tartalmazza a **kutatócsoportok bemutatkozó oldalait**. Minden
csoport egy külön Markdown (`.md`) fájl. Az oldalak a `/kutatocsoportok/...`
címen érhetők el, és a [Kutatás]({{ '/kutatas/' }}) oldalról nyílnak meg
(a csoport nevére kattintva).

A cél egy **egyszerű, könnyen karbantartható** sablon. Ha egy csoportnak saját,
külön honlapja van, nem kötelező itt oldalt fenntartani — elég a Kutatás oldal
kártyájáról odalinkelni. Aki viszont nem akar külön honlapot üzemeltetni, annak
ez a sablon kész megoldást ad.

## Új csoportoldal 3 lépésben

1. Másold le egy meglévő fájlt a `_labs/` mappából (pl.
   `figyelem-es-emlekezet.md`).
2. Nevezd át ékezet nélküli, kötőjeles névre, pl. `vizualis-idegtudomany.md`.
3. Írd át a fejlécet (front matter) és a szöveget, majd commitold. Néhány perc
   múlva élesedik.

Végül a [Kutatás oldalon](kutatas.md) a megfelelő csoport nevét linkeld erre az
oldalra (lásd ott a már meglévő példákat).

## A fájl fejléce (front matter)

A fájl elején, két `---` sor között állnak a beállítások:

```yaml
---
layout: lab                       # mindig "lab"
title: A Csoport Neve Kutatócsoport
pi: Vezető Neve                   # kutatócsoport-vezető
permalink: /kutatocsoportok/url-resze/
email: valaki@ttk.bme.hu          # opcionális
scholar: https://scholar.google...# opcionális
mtmt: https://m2.mtmt.hu/...      # opcionális
orcid: https://orcid.org/...      # opcionális
lab_url: https://...              # opcionális: külső honlap
frissitve: 2026                   # mikor frissült utoljára a tartalom
---
```

Csak a `layout`, a `title` és a `permalink` kötelező; a többi mező elhagyható
(ami üres, az nem jelenik meg). A megadott linkek a fejlécben jelennek meg.

## A tartalom (a fejléc alatt)

A fejléc alatt szabad Markdown szöveg jön. Javasolt, egyszerű felépítés:

```markdown
## Bemutatkozás
Egy-két bekezdés a csoportról.

## Munkatársak
- **Vezető Neve** — kutatócsoport-vezető
- **Tag Neve** — beosztás

## Válogatott publikációk
- Szerző (év). Cím. Folyóirat.
```

### Publikációk: ne másold be a teljes listát

A teljes publikációs listát **ne** itt tartsd karban — az gyorsan elavul.
Sorolj fel 3–5 friss, kiemelt publikációt, a teljes listához pedig linkelj a
Google Scholar / MTMT / ORCID profilra (ezeket a fejlécben add meg). Így az
oldal nem megy tönkre attól, hogy ritkán nyúlsz hozzá.

## `frissitve` mező

Az oldal tetején megjelenik, mikor frissítetted utoljára. Ha hozzányúlsz a
tartalomhoz, írd át (pl. `frissitve: 2026`). Ez segít kiszúrni az elavult
oldalakat.

## Képek (opcionális)

A barebones sablon szándékosan nem kér képeket. Ha mégis szeretnél, töltsd az
`images/` mappába, és így hivatkozz a szövegben:
`![Leírás]({{ site.baseurl }}/images/fajlnev.jpg)`

> Ez a README nem jelenik meg a kész oldalon (a `_config.yml` kizárja).
