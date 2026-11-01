# GitHub-spiekbriefje

## De begrippen

| Woord | Wat is het? |
|---|---|
| **Repository (repo)** | De projectmap op GitHub, met de hele geschiedenis erbij. |
| **`main`** | De officiële versie van je project. |
| **Branch** | Een kopie van `main` waarin je veilig werkt. Een kladversie. |
| **Commit** | Een opgeslagen moment: een foto van je bestanden plus een korte beschrijving. |
| **Push** | Je werk naar GitHub sturen. |
| **Pull request (PR)** | Een verzoek: "mag dit in `main`?" Hier bekijk je de wijzigingen. |
| **Merge** | Samenvoegen. De wijzigingen komen erbij, bij de bron verdwijnt niets. |
| **Revert** | Een commit terugdraaien met een nieuwe commit die het tegenovergestelde doet. |

## De vaste cyclus

1. **Branch maken** vanaf `main`. Geef hem een naam die zegt wat erin zit, bijv. `kleuren-aanpassen`.
2. **Aanpassen en committen** op die branch.
3. **Pull request openen:** tabblad **Pull requests** → **New pull request**.
   - **base** (links) = `main`, dus waar het naartoe gaat.
   - **compare** (rechts) = jouw branch, dus waar het vandaan komt.
   - Ezelsbruggetje: het pijltje `←` wijst naar waar het naartoe gaat.
4. **Bekijken** bij **Files changed**: groen = erbij, rood = eraf.
5. **Mergen:** **Merge pull request** → **Confirm merge**.
6. **Opruimen:** **Delete branch**. Er gaat niets verloren, alles staat in `main`.

## Ahead en behind

Een branch wordt altijd vergeleken met `main`.

- **Ahead:** de branch heeft commits die `main` nog niet heeft. Dat werk staat dus **nog niet** in `main`.
- **Behind:** `main` heeft commits die de branch niet heeft.
- Na een merge staat er vaak **1 behind**. Dat is de merge-commit, die alleen in `main` komt. Niets aan de hand: de branch kan weg.

## Wat kan wel, wat kan niet?

### ✅ Dit kan altijd

- **Een branch verwijderen** na het mergen. De commits blijven bewaard in `main`.
- **Een verwijderde branch terughalen** via de knop **Restore branch** op de pagina van de pull request.
- **Iets terugzetten met de hand:** nieuwe branch, aanpassen, commit, pull request, merge. Dit werkt altijd.
- **Terugkijken:** alle oude versies blijven in de geschiedenis staan (klik op **Commits**).

### ✅ Dit kan meestal

- **Mergen.** Dat lukt als er niet in beide branches op dezelfde plek iets is veranderd.
- **Een losse commit terugdraaien met Revert**, ook een oude, zonder de latere aan te raken.
  Ga naar **Pull requests** → **Closed** → open de PR → knop **Revert**.

### ❌ Wanneer lukt het niet automatisch?

- **Revert of merge lukt niet** als er later op **dezelfde plek of direct ernaast** iets is veranderd. Dat heet een **conflict**.
  - GitHub vergelijkt alleen regels tekst. Het snapt geen CSS of HTML.
  - Liggen twee aanpassingen dicht bij elkaar, dan durft GitHub niet te kiezen en stopt het.
  - **Oplossing:** doe het met de hand (zie hierboven).

### ⚠️ Let op

- **GitHub controleert niet wat iets doet op je website.** Een revert kan technisch lukken en toch iets anders veranderen dan je dacht.
  Voorbeeld: knoppen en h2-koppen delen dezelfde kleur (`--accent`). Draai je de knopkleur terug, dan veranderen de koppen mee.
  Kijk dus altijd even bij **Files changed** voordat je merget.
- **Let op de richting van een pull request.** Staat `main` rechts in plaats van links, dan gaat het de verkeerde kant op.
- **Gebruik geen "reset" op `main`.** Dat wist commits echt uit de geschiedenis. Revert is veiliger.

## Tips

- **Kleine stappen:** één aanpassing per commit. Dan is terugdraaien makkelijker.
- **Duidelijke namen** voor branches en commits, zodat je later nog weet wat het was.
- **Bij nieuwe repo's:** vink **Add a README file** aan, dan staat `main` meteen klaar.
