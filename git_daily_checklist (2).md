
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
