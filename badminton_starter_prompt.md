Find the next available badminton court at 19:00 on a **Tuesday or Thursday**, within 5 km of our house, and give me the direct booking link. Pick the best one (closest/cheapest) and list any runners-up.

## Context already gathered (don't redo this)

- **Home:** Marie Grubbes Allé 16, 2800 Kgs. Lyngby (Buddinge, Gladsaxe Kommune). Coordinates from OpenStreetMap Nominatim: **55.757358, 12.476975**.
- **Network:** needs full network access (WannaSport and Nominatim must be reachable). DAWA/dataforsyningen address API is retired (410), so use Nominatim for geocoding.
- **WannaSport has a free open JSON API, so no HTML scraping is needed:**
  `https://api.wannasport.com/api/open/v1/availability/search?area=<area>&category=badminton&date=YYYY-MM-DD&sort=startTime&page=1&country=dnk&lang=da`
  - Areas that cover our 5 km radius: `gladsaxe`, `lyngby`, `gentofte`, `herlev`.
  - 50 results per page; paginate with `page` / `totalPages`.
  - Each result has `facility.name`, `facility.address`, `startTime` (ISO with +02:00/+01:00), `durationMinutes`, `price.amount`, `available`, `bookableOnline`, `bookingUrl`, `checkedAt`.
  - Its `distanceKm` is measured from the searched area, not from our house, so compute the distance yourself from the home coordinates.
- **Venues within 5 km (straight-line distance from home, computed earlier):**
  | Venue | Address | km | Typical 19:00 price |
  |---|---|---|---|
  | Engelsborghallen | Engelsborgvej 93, Lyngby (WannaSport lists postcode 2000 by mistake, so this distance is the least certain) | ~1.4 | 120 DKK |
  | Idrætsanlæggene i Gladsaxe (Gladsaxe Badmintonhaller, 10 courts) | Gladsaxevej 200, 2860 Søborg | 3.1 | 110 DKK |
  | Gentofte Sportspark | Ved Stadion 10, 2820 Gentofte | 3.1 | 119 DKK |
  | Gentofte Badminton Klub | Ved Stadion 4, 2820 Gentofte | 3.2 | 125–160 DKK |
  | Lyngby Idrætsby | Lundtoftevej 53A, 2800 Lyngby | 3.2 | 120 DKK |
  | Virumhallerne | Geels Plads 40, 2830 Virum | 4.0 | ~110 DKK |
  | Skinderskovhallen | Skinderskovvej 31, 2730 Herlev | 4.3 | 100 DKK |
  | Charlottenlund Badminton | Maltegårdsvej 18, Gentofte | 4.9 | 120 DKK |
  | Kildeskovshallen | Adolphsvej 25, Gentofte | 4.9 | 119 DKK |
  | (Lundtoftehallen, Ravnholmvej 11, is 5.4 km, just outside the limit) | | | |
- **Finding from the scan on 16 Oct 2026 (dates 16–29 Oct):** every Monday–Thursday 19:00 slot within 5 km was fully booked for the whole two weeks; only Friday and weekend 19:00 slots were free. So Tuesday/Thursday 19:00 is scarce, and you will probably need to look further ahead (scan at least 6–8 weeks).
- Courts are usually 60 min. Some halls start on the half hour (for example 18:30 at Skinderskovhallen). Only count slots that start exactly at 19:00, but mention any free 18:30 or 19:30 slots on Tue/Thu as alternatives.
- Bring your own rackets and shuttles. Gladsaxe has free parking with a parking disc.

## What I want back

1. The single next Tuesday or Thursday 19:00 court within 5 km: date, venue, distance, price, and the `bookingUrl`.
2. A short list of the next few alternatives, including near-misses like 18:30 or 19:30.
3. When WannaSport last checked availability (`checkedAt`), so I know how fresh the result is.
