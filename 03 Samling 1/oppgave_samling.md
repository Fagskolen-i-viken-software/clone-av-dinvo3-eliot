# Verkstedoppgave: Segmentering av verktøy med DinoV3 + logistisk regresjon

## Oppgave

Dere skal lage deres egen lille segmenteringsmodell for verktøy. Målet er å gå hele veien fra råbilder til ferdig modell som kan gjenkjenne verktøy i nye bilder.

## Steg-for-steg

### 1. Samle datasett

Som gruppe skal dere samle totalt **30 bilder** av **2–3 forskjellige verktøy** fra prototype-laben.


### 2. Lag masker (labels)

For hvert bilde skal dere lage en **binær maske** (hvit = verktøy, svart = bakgrunn). Hvilket verktøy dere bruker for å lage maskene, bestemmer dere selv.

### 3. Ekstraher features med DinoV3

- Følg eksemplet fra notebooken dere har gått gjennom.
- Kjør segmentering på deres egne bilder.
- Bruk output fra DinoV3 som feature-vektorer.

### 4. Tren logistisk regresjon

- Bruk features (X) og labels (y) fra maskene.
- Tren en logistisk regresjon til å skille mellom verktøy og bakgrunn.

### 5. Test modellen

- Bruk nye bilder (som modellen ikke har sett før).
- Prediker maske for disse bildene.
- Visualiser: vis originalbildet og den predikerte masken.

## Leveranse

### Notebook
Kjør hele prosessen i en Jupyter Notebook.

### GitHub-repo
Push notebook, bilder og masker til deres egen repo.

### README.md skal inneholde:
- Kort sammendrag av hva dere har gjort.
- Hvilket verktøy dere brukte for å lage maskene.
- En illustrasjon/eksempel på resultatet.

## Bonus (frivillig)

- Prøv å lage masker med flere klasser (f.eks. hammer vs. skrutrekker).
- Sammenlign prediksjonene fra deres logistiske modell med segmenteringsresultatene direkte fra DinoV3.

**Mål: erfaring med hele maskinlæringspipeline**: datafangst → annotering → feature-ekstraksjon → modelltrening → testing → dokumentasjon.