# Retirement Flats to Rent near Canterbury — Rightmove Data Collection

## About this file

This file lists every retirement flat/apartment advertised to rent on Rightmove within a 10-mile radius of Canterbury, Kent, as captured on 7 July 2026. The search was restricted to Rightmove's "Retirement" property filter and to the "Flats / Apartments" property type, so age-restricted houses and bungalows that also appear under the retirement filter were deliberately excluded (they are noted at the bottom for context).

---

## The task (for re-running or updating later)

A fresh agent with no memory of the original session can reproduce this collection from the steps below alone.

1. Go to Rightmove's rent homepage: `https://www.rightmove.co.uk/property-to-rent.html`. Dismiss the cookie banner (reject non-essential cookies).
2. In the location search box, type `Canterbury` and select the top autocomplete suggestion **"Canterbury, Kent"**. This assigns the location identifier `REGION^279`. Do not hand-type a region code; Rightmove's codes are not guessable (e.g. `REGION^276` is Campbeltown, not Canterbury).
3. Once you have `REGION^279`, skip the filter UI and go straight to the results URL below. It bakes in three constraints: 10-mile radius (`radius=10.0`), retirement-only (`mustHave=retirement`), and flats/apartments only (`propertyTypes=flat`). It also excludes Let Agreed properties (`includeLetAgreed=false`).
4. Confirm the results header reads **"Retirement Properties To Rent in Canterbury, Kent, flat, within 10 miles"** and that **Filters (1)** is active. This verifies the retirement filter applied.
5. Read the full results with the page-text tool. For each listing extract: price (pcm and pw), address/development, property type label, bedrooms, bathrooms, agent, and date added. Paginate if a "page 2" exists (at time of capture all results fit on a single page).
6. Exclude: any result whose property-type label is not a flat or apartment (the unconstrained retirement search also returns houses and bungalows — a semi-detached house at Orchard Yard, Wingham and a bungalow at London Road, Faversham were present but excluded here). Exclude Let Agreed listings. Exclude sponsored/promoted agent tiles that are not property listings.

**Search URL / starting point:**
```
https://www.rightmove.co.uk/property-to-rent/find.html?locationIdentifier=REGION%5E279&radius=10.0&propertyTypes=flat&includeLetAgreed=false&mustHave=retirement
```

**Cross-check URL (retirement, all property types — to spot flats mis-filed under other type labels):**
```
https://www.rightmove.co.uk/property-to-rent/find.html?locationIdentifier=REGION%5E279&radius=10.0&includeLetAgreed=false&mustHave=retirement
```

**Last run:** 7 July 2026
**Total results at time of capture:** 6 (flat-constrained); 8 across all retirement property types

---

## Retirement flats to rent (within 10 miles of Canterbury)

Sorted lowest to highest monthly rent.

| Price (pcm) | Price (pw) | Development / Address | Type label | Beds | Baths | Agent | Date added |
|-------------|-----------|-----------------------|------------|------|-------|-------|-----------|
| £950 | £219 | Homespire House, Canterbury | Flat | 1 | 1 | Mann Lettings, Canterbury | 15/06/2026 |
| £1,650 | £381 | Abbots Lodge, Canterbury, Kent | Retirement Property | 2 | 1 | Churchill Sales & Lettings, Ringwood | 12/06/2026 |
| £2,935 | £677 | Eastry Place, New Dover Road, Canterbury CT1 3AT | Apartment | 1 | 1 | Flagstones Property Group, London | 08/06/2026 |
| £3,120 | £720 | 35-41 New Dover Road, Canterbury, Kent, CT1 3AT | Retirement Property | 1 | — | McCarthy & Stone, Nationwide | 22/12/2025 |
| £4,370 | £1,008 | Eastry Place, New Dover Road, Canterbury CT1 3AT | Apartment | 2 | 2 | Flagstones Property Group, London | 08/06/2026 |
| £4,370 | £1,008 | 35-41 New Dover Road, Canterbury, Kent, CT1 3AT | Retirement Property | 2 | — | McCarthy & Stone, Nationwide | 06/11/2025 |

Note: Eastry Place and 35-41 New Dover Road are both on New Dover Road, CT1 3AT, and are the same McCarthy & Stone development marketed by two different agents (Flagstones and McCarthy & Stone direct), which is why the 1-bed and 2-bed appear twice at different prices. Treat these as duplicate stock, not four separate homes.

---

## Excluded — retirement, but not flats (for context only)

These appeared in the all-property-types retirement search and were excluded because they are not flats/apartments.

| Price (pcm) | Address | Type label | Beds | Reason excluded |
|-------------|---------|------------|------|-----------------|
| £1,500 | Orchard Yard, Wingham, Canterbury | Semi-Detached | 3 | House, not a flat |
| £1,650 | London Road, Faversham, ME13 | Bungalow | 1 | Bungalow, not a flat |

---

## Summary / notes

- Six retirement flats currently to rent within 10 miles of Canterbury, but effectively **four distinct homes** once the New Dover Road duplication is collapsed.
- Rent distribution (all six rows): one at £950, one at £1,650, one at £2,935, one at £3,120, two at £4,370. Average £2,899 pcm; median £3,027 pcm.
- Cheapest by a wide margin is Homespire House at £950 pcm (1-bed, central Canterbury, first floor, electric heating, communal garden/lounge).
- The two most expensive (£4,370) are 2-bed units on New Dover Road; the McCarthy & Stone stock uses assured periodic tenancies you can rent for as long as you want.
- Only one result sits outside Canterbury city itself within the flat set — none, in fact; all six flats are Canterbury-city addresses. The out-of-town retirement stock (Wingham, Faversham) is houses/bungalows, not flats.

---

## Notes and caveats

- Data captured on: 7 July 2026.
- Exclusion rules applied: property-type label must be Flat / Apartment / (retirement-labelled flats); houses, bungalows, land, and commercial excluded. Let Agreed excluded (`includeLetAgreed=false`). Promoted agent tiles ignored.
- Some listings carry a generic "Retirement Property" type label rather than "Flat"; these were kept because their descriptions confirm they are apartments. If re-running strictly on the `propertyTypes=flat` URL, the "Retirement Property"-labelled apartments still appear because Rightmove classifies them as flats internally.
- Two older McCarthy & Stone listings (dated Dec 2025 and Nov 2025) are long-standing and may since have let; verify availability before acting.
- Bedroom/bathroom counts for the McCarthy & Stone rows show beds only; bathroom count was not stated on the results page.
- Prices are asking rents and exclude service charges, ground rent, and deposits, which are typically significant for retirement developments.
- All results fit on a single page at capture time, so the "first 2 pages" scope was fully satisfied with no page 2 to collect.

---

*Source: Rightmove — https://www.rightmove.co.uk/property-to-rent/find.html?locationIdentifier=REGION%5E279&radius=10.0&propertyTypes=flat&includeLetAgreed=false&mustHave=retirement*
*Captured: 7 July 2026 — 6 results across 1 page*
