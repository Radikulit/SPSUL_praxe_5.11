# Jídelníček: název jídla, alergeny (čísla)

## Popis nástroje
Nástroj slouží ke zpracování a strukturovanému zobrazení denního nabídkového menu školní jídelny. Umožňuje uživatelům snadno projít dostupná jídla včetně jejich názvu a přiřazených číselných kódů alergenů. Díky standardizovanému formátu usnadňuje filtrování pokrmů pro osoby se specifickými dietními omezeními

## Schéma výstupu
```json
{
  "nazev_jidla": "string",
  "kategorie": "polevka | hlavni_jidlo | dezert | napoj | jine",
  "alergeny": [ "number" ]
}