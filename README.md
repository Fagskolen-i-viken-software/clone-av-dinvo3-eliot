# Introduksjon til Nevrale Nettverk

Velkommen til **«Introduksjon til nevrale nettverk»**, et praktisk kurs som inngår i emnet  
*«Introduksjon til KI og maskinlæringsmodeller»*.

Dette kurset tar deg gjennom en stegvis introduksjon til maskinlæring og nevrale nettverk med praktisk programmering i Python.

---

## Mål for kurset

- **Forstå** hva maskinlæring (ML) og nevrale nettverk (NN) er, og se eksempler på bruk i virkelige prosjekter.  
- **Bygge, trene og evaluere** egne modeller i Python – først klassiske ML-metoder, deretter enkle nevrale nettverk.  
- **Beherske verktøy** som Jupyter Notebook, VS Code og GitHub i det daglige arbeidet.

---

## Undervisningsplan 

PDF versjon: [Fremdriftsplan pdf](./ressurser/Fremdriftsplan.pdf)

| Uke | Tema / Kapittel                                          | Innhold                                                                 |
|-----|----------------------------------------------------------|-------------------------------------------------------------------------|
| 34 | Introduksjon til faget                                   | Hva er KI og ML? Etikk, bruksområder, verktøy                          |
| 35 | Kap. 1 – The ML Landscape (del 1)                        | ML-typer, supervised/unsupervised, batch/online, modelltyper           |
| 36 | Kap. 1 – The ML Landscape (del 2)                        | Overfitting, underfitting, bias/variance, evaluering, generalisering   |
| 37 | Kap. 2 – End-to-End ML Project (del 1)                   | Datasett, train/test split, prosessforståelse                          |
| 38 | Kap. 2 – End-to-End ML Project (del 2)                   | Pipelines, transformasjoner, prosjektfremdrift                        |
| 39 | **FYSISK SAMLING** Prosjekt | prosjekt|
| 40 | _Høstferie_ || | 
| 41 | Kap. 6 – Decision Trees                                  | Beslutningsgrenser, regularisering              |
| 42 | Kap. 10 – Nevrale nettverk (del 1)                       | Perceptron, MLP, fremoverføring og tilbakepropagering                 |
| 43 | Kap. 10 – Nevrale nettverk (del 2)                       | Keras, Sequential API, TensorBoard                                    |
| 44 | Kap. 10 – Nevrale nettverk (del 3)                       | Klassifisering, regresjon, aktiveringsfunksjoner                      |
| 45 | Kap. 10 – Nevrale nettverk (del 4)                       | Hyperparametertuning, dropout, batch size, lag                        |
| 46 | **FYSISK SAMLING**                                       | Fokus på klassiske ML-metoder og anvendelse                           |
| 47 | Repetisjon/gruppeoppgave/arbeidskrav                     | -                               |
| 48 | Repetisjon/gruppeoppgave/arbeidskrav                     | -              |
| 49 | Repetisjon/gruppeoppgave/arbeidskrav                     | - |
| 50 | Vurderingsuke                                              |- |
| 51 | Vurderingsuke                                              |- |
---

## Lenker og videre ressurser

- **Kursbok:** [Hands-On Machine Learning with Scikit-Learn, Keras and TensorFlow (2nd ed.)](./ressurser/Hands-On_Machine_Learning_with_Scikit-Learn-Keras-and-TensorFlow-2nd-Edition-Aurelien-Geron.pdf)
- 🧪 **Kursbibliotek (Python):**
  - [scikit-learn](https://scikit-learn.org/)
  - [keras](https://keras.io/)
  - [tensorflow](https://www.tensorflow.org/)
  - [pandas](https://pandas.pydata.org/)
  - [matplotlib](https://matplotlib.org/)

## Verktøy du trenger

| Verktøy | Beskrivelse | Nedlasting |
|--------|-------------|------------|
| **Visual Studio Code** | Kodeditoren vi bruker (med *Jupyter*-utvidelsen) | [code.visualstudio.com](https://code.visualstudio.com/) |
| **Python ≥ 3.10** | Programmeringsspråket for kurset | [python.org/downloads](https://www.python.org/downloads/) |
| **Jupyter Notebook** | Kjørbar notatbok for kode + tekst | `pip install notebook` |
| **Git & GitHub** | Versjonskontroll og deling av prosjekter | [git-scm.com](https://git-scm.com/downloads) |

> **Tips:** Bruk `venv` for å lage isolerte Python-miljøer i prosjektet.

---

## Før du starter

1. **Installer** VS Code, Python og Git.  
2. Åpne VS Code → Extensions → søk etter og installer **"Jupyter"**.  
3. Lag ny fil (`start.ipynb`) og kjør første celle:

```python
print("Hei! Nå er du klar til å lære maskinlæring 🚀")
