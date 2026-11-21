# Re-engineering the Purifaaya Water Filter

Our entry for the Re-Engineering Challenge at the Waterloo Engineering Competition (WEC), Fall 2026.

The challenge was to take an existing product and re-engineer it for a better or new use. We picked the Purifaaya, a household ceramic water filter made by SPOUTS of Water in Uganda. We kept the part that already works well, the SPOUTS ceramic pot, and designed a new housing around it that:

- filters faster, and keeps the flow steady instead of slowing down as the water level drops
- removes fluoride, which the original filter can't do
- can add zinc to the water as an option

![Isometric view with labelled parts](images/isometric.png)

## How it works

Water moves from top to bottom through five stages:

1. **Sealed raw-water reservoir.** You fill it through an airtight cap. A feed tube keeps the water in the ceramic pot at one constant level (the same idea as a Mariotte bottle), so the flow doesn't drop as the reservoir empties.
2. **SPOUTS ceramic pot.** The same pot the Purifaaya uses. It removes about 99.99% of pathogens. We buy it from SPOUTS, so their local factory stays part of the supply chain.
3. **Bone char basket.** A wide, shallow bed of granular bone char removes fluoride without slowing the flow. Households refill it with bags of bone char made by local butchers and abattoirs.
4. **Optional zinc plate.** It sits under the bone char, because the bone char would strip the zinc out if it came first. Households that don't want zinc use a blank plate.
5. **Covered storage tank.** Holds the clean water, with a tap at the front and a drain plug at the back for cleaning.

![Front section view](images/section-front.png)

![Isometric section view](images/section-isometric.png)

## Size

About 1300 mm tall and 460 mm wide at the base, and about 22 kg empty with the filter media in (no water).

![Dimensions](images/dimensions.png)

## Engineering numbers

**Flow.** Flow through the ceramic follows Darcy's law, `Q = K * A * dh / L`, so a steady water level gives a steady flow. We estimate about 7 L/hr, compared to 4.5 to 5 L/hr for the Purifaaya. The 1.5x gain is an assumption we still need to test.

**Bone char.** Bone char holds about 2 mg of fluoride per gram. At 70 L a day and 3 mg/L of fluoride, that's 210 mg of fluoride a day, so an 8.4 kg charge lasts about 80 days (about 160 days at 1.5 mg/L).

**Zinc.** The target is about 3.5 mg/L, the same level LifeStraw Family gave in a field trial in Kenya. We sized it for the worst case (a fresh plate, the warmest water and the slowest flow) and checked it against the upper intake limit for a toddler. Water that sits in the plate overnight (about 0.2 L) gets diluted about 100 times in the 20 L tank. The zinc plate is sized to run out at the same time as the bone char, so there's only one refill.

## Compared to the Purifaaya

| | Purifaaya | Our design |
|---|---|---|
| Pathogens removed | 99.99% | 99.99% (same ceramic) |
| Fluoride | Not removed | Below 1.5 mg/L (WHO limit) |
| Flow | 4.5 to 5 L/hr, drops as the water level falls | About 7 L/hr, steady |
| Nutrition | None | Optional zinc, about a third of a child's daily needs |
| Salt | Not removed | Not removed |

## Maintenance

- Every 14 days: scrub the ceramic pot. This is the same as the Purifaaya, but the steady flow should mean less clogging.
- About every 3 months: refill the bone char and swap the zinc plate at the same time.

## Design decisions

- **No salt removal.** No method that works without fuel or power can do it at this flow rate, and salty water is mostly limited to the crater lake areas of the Rift Valley.
- **Only zinc.** It's the one nutrient with field evidence behind adding it through a filter. Iron causes taste and staining problems, and vitamins don't stay stable in water.
- **Household unit, not a community system.** It compares directly with the Purifaaya, and the bone char refill bags already create a local supply chain.
- **No homemade bone char.** Bone that isn't charred properly makes the water taste and smell bad. Doing it right takes a kiln running for days.
- **No water treatment sachets.** They cost about 10 times more per litre, are imported, and people often don't buy them again.

## Who it helps

- **Families:** protection from fluoride, faster water and optional zinc.
- **SPOUTS:** our design buys their ceramic pots instead of competing with them.
- **Local butchers and abattoirs:** new income from turning waste bones into bone char.
- **The environment:** no fuel needed, and the bone char comes from food waste.

## CAD

The model was built in SolidWorks. Open `cad/00_WEC_Filter_Assembly.SLDASM` to see the full assembly, which is made of the 11 part files next to it.
