# Beton — kalkulačka směsi

Jednosouborová mobilní kalkulačka na ruční míchání betonu. Bez závislostí, bez buildu,
bez backendu — celé je to jeden `index.html` s inline CSS a JS.

**Živě: https://culhy.github.io/beton-kalkulacka/**

## Co umí

- objem betonu v m³
- volba pevnostní třídy (B7,5 – B30) s typickým použitím
- doporučené receptury k dané třídě, nebo **vlastní poměr** → z něj odhad pevnostní třídy
- výsledek živě: cement, písek, kamenivo, rozsah záměsové vody
- přepínač **kg + l ↔ lopaty** (u cementu i fanky a pytle)
- přepínač **celkem ↔ na 1 míchačku**
- vše se ukládá do localStorage, tlačítko Reset
- jedna obrazovka bez scrollování; layout se sám zmenší, aby se vešel

## Z čeho to počítá

| Veličina | Hodnota |
|---|---|
| sypná hmotnost cementu | 1200 kg/m³ |
| sypná hmotnost písku | 1600 kg/m³ |
| sypná hmotnost kameniva | 1500 kg/m³ |
| sypký objem → zhutněný beton | × 1,55 (s kamenivem), × 1,35 (bez) |
| záměsová voda | kg cementu × w/c dané třídy |
| lopata | 1,7 l (počty se zaokrouhlují na půl lopaty) |
| fanka | 1,5 l |
| kolečko | 60 l |
| pytel cementu | 25 kg |
| míchačka | buben 125 l, nasaditelných ~45 % → násada ~56 l |

Odhad třídy z vlastního poměru jde přes dávku cementu na m³ (prahy 165 / 187 / 222 / 267 /
312 / 355 kg/m³).

## Čím to není

Orientační pomůcka pro ruční míchání na stavbě, ne návrh betonu podle normy. Objemový poměr
a w/c samy o sobě třídu nezaručí — záleží na druhu cementu, zrnitosti a vlhkosti kameniva,
hutnění a ošetřování. U směsí bez kameniva (mazanina, potěr) aplikace třídu betonu záměrně
neuvádí, protože o beton nejde.
