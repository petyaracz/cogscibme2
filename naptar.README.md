# Naptár kezelése (`naptar.md` oldal)

A **Naptár** menüpont (`/naptar/`) egy beágyazott Google Naptárt jelenít meg:
a félév menetrendjét és a tanszéki eseményeket. A naptár tartalmát nem ezen az
oldalon, hanem **közvetlenül a Google Naptárban** szerkesztjük; az oldal csak
megjeleníti azt. Egy esemény hozzáadásához tehát nem kell a honlaphoz nyúlni.

## Hogyan működik

A `naptar.md` fájl egyetlen `<iframe>`-et tartalmaz, amely a Google Naptár
beágyazott nézetére mutat. A beágyazás URL-jében szerepel a naptár azonosítója
(`...@group.calendar.google.com`). Ha a naptárban felveszel egy eseményt, az
néhány percen belül megjelenik az oldalon — a honlapot **nem kell** újra
buildelni.

## FONTOS: a naptárnak nyilvánosnak kell lennie

A beágyazás csak akkor látszik a látogatóknak, ha a naptár nyilvános:

1. Google Naptár → a bal oldali listában vidd az egeret a naptár fölé →
   három pont → **Beállítások és megosztás**.
2. **Hozzáférési engedélyek** szakasz → pipáld be a
   **„Nyilvánossá tétel"** lehetőséget. Ha a címeket is mutatni szeretnéd,
   válaszd az „Összes esemény részletei" opciót.

Ha ez nincs bekapcsolva, a látogatók „a naptár nem érhető el" üzenetet látnak.

## Esemény felvétele

Nyisd meg a Google Naptárt, és a megfelelő naptárba vegyél fel eseményt a
szokásos módon (cím, időpont, helyszín, leírás). Ennyi — az oldal automatikusan
frissül, nem kell commitolni.

## Több naptár megjelenítése egyszerre

Egy beágyazásban több naptár is mutatható, színkódolva (pl. külön naptár a
BSc-nek és az MSc-nek). Ehhez a `naptar.md` fájlban az `<iframe src="...">`
URL-jét kell bővíteni. A kommentezett útmutató ott, a fájlban is megtalálható,
közvetlenül az `<iframe>` fölött.

Röviden:

1. Szerezd meg az új naptár **azonosítóját**: Google Naptár → az adott naptár
   **Beállítások és megosztás** → **A naptár integrálása** szakasz →
   **Naptár-azonosító** (pl. `valami@group.calendar.google.com`).
2. A `naptar.md` `src="..."` értékébe írj be még egy `&src=` paramétert. Az
   `@` jelet cseréld `%40`-re:

   ```
   &src=UJ_NAPTAR_ID%40group.calendar.google.com
   ```

3. (Opcionális) színezéshez minden `&src=` után tehetsz egy
   `&color=%23RRGGBB` paramétert (a `%23` a `#` jel). A sorrend számít:
   az első `color` az első `src`-hez tartozik.

Példa két naptárral, színekkel (az `src` értéke **egyetlen sorban**, szóköz és
sortörés nélkül legyen):

```
src="https://calendar.google.com/calendar/embed?ctz=Europe%2FBudapest&showTitle=0&src=ELSO_ID%40group.calendar.google.com&color=%230b8043&src=MASODIK_ID%40group.calendar.google.com&color=%233f51b5"
```

Minden megjelenített naptárnak külön-külön **nyilvánosnak** kell lennie (lásd
fent).

## Megjelenés finomhangolása (opcionális)

Az `src` URL-be további paraméterek tehetők, `&` jellel elválasztva:

| Paraméter         | Mit csinál |
|-------------------|-----------|
| `mode=MONTH`      | Alapnézet: `MONTH`, `WEEK` vagy `AGENDA` (lista). |
| `showTitle=0`     | Elrejti a naptár címét (már beállítva). |
| `showPrint=0`     | Elrejti a nyomtatás gombot. |
| `showTabs=0`      | Elrejti a nézetváltó füleket. |
| `showCalendars=0` | Elrejti a naptárlistát. |
| `ctz=Europe%2FBudapest` | Időzóna (már beállítva). |

A megjelenítő doboz magassága a `naptar.md` alján lévő kis `<style>` blokkban
állítható (`height`).

## Módosítás után

A naptár **tartalmának** változásához (események) nem kell semmit commitolni.
Csak akkor kell a `naptar.md`-t módosítani és commitolni, ha **új naptárt adsz
hozzá** vagy a megjelenést állítod. A `main` ágra pusholt módosítások néhány
percen belül élesednek.

> Ez a README nem jelenik meg a kész oldalon (a `_config.yml` kizárja).
