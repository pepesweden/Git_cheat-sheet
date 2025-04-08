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
