# ✅ Daily Git Checklist

## 📥 Start of Day
1. Navigate to your project folder:
   ```bash
   cd ~/path/to/project
   ```
2. Pull latest changes to stay in sync:
   ```bash
   git pull
   ```

## 🛠️ During Work
3. Make code changes
4. Check status:
   ```bash
   git status
   ```
5. Stage changes:
   ```bash
   git add <filename>
   # or
   git add .
   ```
6. Commit changes:
   ```bash
   git commit -m "feat: your message"
   ```
7. Use diff tools:
   ```bash
   git diff              # unstaged
   git diff --cached     # staged
   git diff origin/main  # local vs GitHub
   ```

## ☁️ End of Day
8. Push changes to GitHub:
   ```bash
   git push



## ✅ Git Init Checklist – Lägg till ett nytt projekt i GitHub

```bash
# 1. Navigera till din projektmapp
cd ~/path/to/your/project

# 2. Initiera ett nytt Git-repo
git init

# 3. Lägg till alla filer i staging
git add .

# 4. Gör din första commit
git commit -m "init: första commit"

# 5. Skapa ett nytt GitHub-repo via GitHub CLI och koppla det
gh repo create ditt-användarnamn/ditt-repo --private --source=. --remote=origin --push

# Alternativ: om du skapade repositoriet manuellt på GitHub
git remote add origin git@github.com:username/repo.git
git push -u origin main

# 6. Verifiera att remote är korrekt kopplad
git remote -v
```

 🧠 Bonus: Undo & Rollback
   ```
- Unstage a file:
  ```bash
  git restore --staged <file>
  ```
- Restore file to last commit:
  ```bash
  git restore <file>
  ```
- Undo last commit, keep changes:
  ```bash
  git reset --soft HEAD~1
  git reset --mixed HEAD~1
  ```
- Panic reset everything:
  ```bash
  git reset --hard HEAD
  ```
- Stop tracking all files added (if you added gitignore for ex)
  ```bash
  git rm -r --cached .
  ```


## 🔁 Rollback Efter Push (Force Push)
Scenario: Du har pushat en commit du vill ångra.

```bash
# 1. Skapa test-commit
echo "test" >> test.txt
git add test.txt
git commit -m "test: pushed by mistake"
git push

# 2. Ångra senaste commit lokalt
git reset --soft HEAD~1

# 3. Force push till GitHub för att radera commiten
git push --force

# 4. Ta bort filen helt (om du inte vill ha kvar den lokalt)
git restore --staged test.txt
rm test.txt
```


---
## 🔁 BONUS: Rollback efter `push` (force reset)
### Steg-för-steg för att ångra en commit som redan är pushad:
```bash
# 1. Skapa en test-commit och pusha den
echo "test" >> file.txt
git add file.txt
git commit -m "oops: bad push"
git push

# 2. Ångra senaste commit (lokalt, behåll staging)
git reset --soft HEAD~1

# 3. Force push för att ta bort commit från GitHub
git push --force

# 4. Rensa bort staged file om du inte vill ha kvar den
git restore --staged file.txt
rm file.txt
```
> 🧠 Detta återställer GitHub till före din senaste commit – och raderar filen lokalt.

# 🚀 Manuell Clone av Template-projekt
## 📋 Snabbversion

Stå i mappen med projekt
```bash
gh repo create USERNAME/<project_name> --template pepesweden/automation-project_template --private
git clone git@github.com:pepesweden/pdf_generator.git
```


---

