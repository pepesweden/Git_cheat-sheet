# 🌱 Git Branching Cheat Sheet (Solo Developer)

## 🧠 Grundprincip
Du jobbar i **samma projektmapp**, men växlar Git-branch – ingen kopiering behövs.

## 🔁 Vanligt arbetsflöde
```bash
# 1. Starta från main
git checkout main

# 2. Skapa och byt till en ny branch
git checkout -b feat/ny-funktion

# 3. Jobba på din grej, gör commits
git add .
git commit -m "feat: bygg ny funktion"

# 4. Testa och iterera tills du är nöjd
# ...

# 5. Gå tillbaka till main och mergea in
git checkout main
git merge feat/ny-funktion

# 6. Pusha main till GitHub
git push

# (valfritt) 7. Ta bort din branch lokalt
git branch -d feat/ny-funktion
```

## 💡 Tips
- Använd prefix som `feat/`, `fix/`, `refactor/` för tydlighet
- Byt alltid tillbaka till `main` innan du skapar nya branches
- Du kan när som helst byta branch med `git checkout <branch>`

# 🧪 Solo Git Workflow – Med säkerhetsnät

## ✅ Steg-för-steg
```bash
# 1. Gå till main och hämta senaste från GitHub
git checkout main
git pull

# 2. Skapa och byt till ny branch
git checkout -b feat/ny-grej
# (Här jobbar du fritt – testa, ändra, bygg)

# 3. Om det går sönder – rulla tillbaka:
git checkout main
git branch -D feat/ny-grej

# 4. Om det fungerar – committa som vanligt
git add .
git commit -m "feat: ny grej"

# 5. Gå tillbaka till main och mergea in
git checkout main
git merge feat/ny-grej

# 6. Pusha main till GitHub
git push
```

## 💡 Tips
- Inga separata PRs behövs om du jobbar solo
- Det är fortfarande bra vana att alltid utgå från `main`
- Använd prefix som `feat/`, `fix/`, `test/` i branch-namn för struktur

# 🔀 Mini GitHub Pull Request Cheat Sheet (för central merge)

## ✅ Steg-för-steg
```bash
# 1. Utgå från main
git checkout main
git pull

# 2. Skapa ny branch för ändringen
git checkout -b feat/ny-funktion

# 3. Gör ändringar och committa
git add .
git commit -m "feat: implementera ny funktion"

# 4. Pusha upp din branch till GitHub
git push -u origin feat/ny-funktion
```

## 📝 5. Skapa Pull Request på GitHub
- Gå till repo på GitHub
- Klicka på “Compare & pull request”
- Skriv titel och beskrivning
- Bekräfta → [Create pull request]

## ✅ 6. Mergning
- När PR:n är granskad eller godkänd (även av dig själv om du jobbar solo)
- Klicka på [Merge pull request]
- Ta bort branch (valfritt)

## 🧹 7. Städa lokalt efter merge
```bash
git checkout main
git pull
git branch -d feat/ny-funktion
```
