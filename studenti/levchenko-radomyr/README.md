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
```json

nazev_jidla – název pokrmu nebo nápoje, např. "Svíčková na smetaně", "Čočková polévka". null, pokud text název neuvádí.

kategorie – zařazení jídla do kategorie: polevka, hlavni_jidlo, dezert, napoj nebo jine. null, pokud ji nelze určit.

alergeny – pole číselných kódů alergenů (1–14) obsažených v pokrmu, např. [1, 3, 7]. Pokud pokrm žádné alergeny neobsahuje nebo nejsou uvedeny, vrací se prázdné pole [].

##Pravidla porovnávání

nazev_jidla: nerozlišuje se velikost písmen a přebytečné mezery na začátku/konci se ignorují ("svíčková" = "Svíčková" = " Svíčková ").

kategorie: porovnává se jako přesný řetězec z definovaného výčtu (polevka, hlavni_jidlo, dezert, napoj, jine).

alergeny: porovnává se jako množina čísel – na pořadí čísel v poli nezáleží, duplicity se ignorují a ignoruje se původní formátování zápisu v textu (např. "(1, 3, 7)" = "alergeny: 1,3,7" = [1, 3, 7])