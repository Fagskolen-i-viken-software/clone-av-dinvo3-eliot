# Git & GitHub – kort veileder

## Hva er hva (kort)
- **Git**: Versjonskontroll på din maskin. Lar deg spore endringer, gå tilbake i tid, jobbe i brancher.
- **GitHub**: Tjeneste i skyen for å lagre Git-repoer, samarbeide (issues, pull requests) og dele kode.

> Merk: Med **triage**-tilgang i organisasjonens repo kan du **se, klone, hente (pull/fetch)** – men **ikke pushe**. Du kan derimot **lage egne repoer** i din konto/bruker og pushe dit.

---

## 1) Sett opp Git (CLI)

### 1. Installer
- **Windows/macOS**: Last ned fra [git-scm.com](https://git-scm.com) og installer med standardvalg.
- **Linux**:  
  ```bash
  # Debian/Ubuntu
  sudo apt update && sudo apt install -y git
  # Fedora
  sudo dnf install -y git
  ```

### 2. Konfigurer global identitet
```bash
git config --global user.name "Ditt Navn"
git config --global user.email "din.epost@example.com"
git config --global init.defaultBranch main
```

### 3. Autentisering (velg én)
**A. HTTPS (enkelt)**
- Når du senere pusher til *eget* repo, vil Git spørre om brukernavn + Personal Access Token (PAT).  
  Tips: Lag PAT under GitHub → Settings → Developer settings → **Personal access tokens**.

**B. SSH (ofte best på sikt)**
```bash
# generer nøkkel (trykk Enter på alle spørsmål)
ssh-keygen -t ed25519 -C "din.epost@example.com"
# kopier nøkkelen til utklippstavle
# Windows (PowerShell):
Get-Content $env:USERPROFILE\.ssh\id_ed25519.pub | Set-Clipboard
# macOS:
pbcopy < ~/.ssh/id_ed25519.pub
# Linux:
xclip -sel clip < ~/.ssh/id_ed25519.pub  # ev. bruk cat og kopier manuelt
```
- Lim inn på GitHub → Settings → **SSH and GPG keys** → *New SSH key*.
- Test:
```bash
ssh -T git@github.com
```

---

## 2) Klient: GitHub Desktop (GUI)

1. Last ned og installer: [desktop.github.com](https://desktop.github.com)  
2. **Sign in** med GitHub-kontoen din.  
3. **Clone a repository**:
   - Velg organisasjonsrepo → *Clone* (du får lese/klone med triage).
4. **Fetch origin / Pull** for å hente siste endringer.
5. For *eget* repo:
   - *File → New repository…* for å lage lokalt, deretter *Publish repository* til GitHub.
   - Gjør endringer → **Commit to main** → **Push origin**.

---

## 3) Grunnleggende Git-kommandoer

### Klone og hente (tillatt med triage)
```bash
# klone et repo (HTTPS eller SSH)
git clone https://github.com/org/repo.git
cd repo

# sjekk status og logg
git status
git log --oneline --graph --decorate --all

# hent og slå sammen endringer fra fjern (origin/main)
git pull origin main

# hent referanser uten å slå sammen (oversikt over nye commits/brancher)
git fetch origin
```

### Branching og navigasjon (lokalt)
```bash
# liste brancher
git branch

# lag ny branch
git switch -c feature/xyz
# bytt branch
git switch main
```

> Med triage på org-repo får du **feil ved push**:
```bash
git push origin feature/xyz
# -> forventet "permission denied" eller "protected branch" i org-repo
```

### Jobbe i eget repo (du kan pushe)
```bash
# opprett ny mappe og repo
mkdir mitt-prosjekt && cd mitt-prosjekt
git init
echo "# Mitt prosjekt" > README.md
git add .
git commit -m "Init"

# koble til fjernrepo (erstatt URL med ditt repo)
git remote add origin https://github.com/<bruker>/mitt-prosjekt.git

# første push (opprett main på GitHub)
git branch -M main
git push -u origin main
```

### Vanlige daglige kommandoer
```bash
# legg til endringer i staging
git add <fil>        # eller: git add .
# lag commit
git commit -m "Beskriv hva du endret"
# push til ditt repo
git push

# se forskjeller før commit
git diff             # arbeidsområde
git diff --staged    # det som er staged
```

---

## 4) .gitignore (valgfritt, men lurt)
Legg til en `.gitignore` for å utelate midlertidige filer, f.eks.:
```
# Python/Jupyter
__pycache__/
.ipynb_checkpoints/
.env
*.pyc

# OS
.DS_Store
Thumbs.db
```
Opprett filen og committ den som vanlig:
```bash
echo "__pycache__/" >> .gitignore
git add .gitignore
git commit -m "Add .gitignore"
```

---

## 5) Typiske feilmeldinger & raske løsninger
- **permission denied / 403 ved push til org-repo**: Forventet med triage. Push kun til **eget** repo eller opprett en fork og bruk Pull Request.
- **Your branch is behind ‘origin/main’**:  
  ```bash
  git pull --rebase origin main
  ```
- **Merge conflicts**: Åpne filene, løs konflikter (<<<<<<<, =======, >>>>>>>), deretter:
  ```bash
  git add <filer>
  git commit
  ```

---

## 6) Anbefalt flyt for dere (triage i org, full tilgang i egne repo)
1. **Se/klone** org-repo (analyse, oppgaveløsning lokalt).  
2. **Lag et eget repo** under din GitHub-bruker for eget arbeid – push dit.  
3. Ønsker du å bidra tilbake? **Fork** org-repo → gjør endringer i forken → **Pull Request** til org-repo.

---

## 7) “Cheat sheet” (kort)
```bash
# setup
git config --global user.name "Navn"
git config --global user.email "epost@example.com"

# få kode
git clone <url>
git pull origin main

# arbeid
git switch -c feature/xyz
git add .
git commit -m "Kort, presis melding"

# til eget repo
git push -u origin feature/xyz
```

> Trenger du GUI? Bruk **GitHub Desktop**: *Clone → Commit → Push* for egne repoer, *Fetch/Pull* for org-repoer.
