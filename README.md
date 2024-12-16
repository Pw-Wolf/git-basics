# GIT Cheatsheet: Rad s Working Directory, Staging Area i Repository

## Osnovne komande
- **Napravi novi Git repozitorij**
  ```bash
  git init
  ```
- **Prikaz trenutnog stanja repozitorija**
  ```bash
  git status
  ```
- **Povijest svih commitova**
  ```bash
  git log
  git log --oneline
  ```
- **Promjena zadanog editora za Git**
  ```bash
  git config --global core.editor "code --wait"
  ```

## Dodavanje i commitanje
- **Dodavanje fajla u staging**
  ```bash
  git add <file-name>
  ```
- **Dodavanje svih fajlova u trenutnom direktoriju**
  ```bash
  git add .
  ```
- **Kreiranje commita s porukom**
  ```bash
  git commit -m "<commit-message>"
  ```
- **Dodavanje i commit u jednom koraku**
  ```bash
  git commit -a -m "<commit-message>"
  ```
- **Izmjena prethodnog commita**
  ```bash
  git commit --amend
  ```

## Grane (Branches)
- **Prikaz svih grana**
  ```bash
  git branch
  ```
- **Kreiranje nove grane**
  ```bash
  git branch <branch-name>
  ```
- **Prebacivanje na drugu granu**
  ```bash
  git switch <branch-name>
  ```
  - *Stara komanda:* `git checkout <branch-name>`
- **Kreiranje i prebacivanje na novu granu**
  ```bash
  git switch -c <branch-name>
  ```
- **Brisanje grane**
  - Mekano brisanje:  
    ```bash
    git branch -d <branch-name>
    ```
  - Grubo brisanje:  
    ```bash
    git branch -D <branch-name>
    ```
- **Preimenovanje grane**
  ```bash
  git branch -m <old-name> <new-name>
  ```

## Spajanje grana (Merge)
- **Spajanje grane u trenutnu granu**
  ```bash
  git switch master
  git merge <branch-name>
  ```

## Razlike (Diff)
- **Prikaz promjena koje nisu staged**
  ```bash
  git diff
  ```
- **Prikaz razlike između HEAD i trenutnih promjena (staged i unstaged)**
  ```bash
  git diff HEAD
  ```
- **Prikaz staged promjena**
  ```bash
  git diff --staged
  git diff --cached
  ```
- **Razlike u specifičnom fajlu**
  ```bash
  git diff HEAD <file-name>
  ```
- **Razlike između dva commita**
  ```bash
  git diff <commit-1>..<commit-2>
  ```
- **Razlika između HEAD-a i prethodnog commita**
  ```bash
  git diff HEAD HEAD~1
  ```

## Privremeno spremanje promjena (Stash)
- **Spremanje promjena bez commitanja**
  ```bash
  git stash
  ```
- **Izvlačenje spremljenih promjena**
  ```bash
  git stash pop
  ```

## Resetiranje promjena
- **Odbacivanje trenutnih promjena**
  ```bash
  git restore <file-name>
  ```
  - *Stara komanda:* `git checkout -- <file-name>`
- **Izmjene s drugog commita**
  ```bash
  git restore --source <commit-hash> <file-name>
  ```
- **Makni fajl iz staginga (unstage)**
  ```bash
  git restore --staged <file-name>
  ```
- **Resetiranje na određeni commit**
  - Samo iz repozitorija:
    ```bash
    git reset <commit-hash>
    ```
  - Iz repozitorija i radnog prostora:
    ```bash
    git reset --hard <commit-hash>
    ```

## Povrat promjena (Revert)
- **Revertanje specifičnog commita**
  ```bash
  git revert <commit-hash>
  ```

## Rad s udaljenim repozitorijima (Remote)
- **Kloniranje udaljenog repozitorija**
  ```bash
  git clone <repo-url>
  ```
- **Prikaz udaljenih destinacija**
  ```bash
  git remote -v
  ```
- **Promjena imena remote destinacije**
  ```bash
  git remote rename <old-name> <new-name>
  ```
- **Brisanje remote destinacije**
  ```bash
  git remote remove <name>
  ```
- **Slanje promjena na remote**
  ```bash
  git push <remote> <branch>
  ```
- **Postavljanje upstream-a za branch**
  ```bash
  git push -u <remote> <branch>
  ```
- **Skidanje promjena s remote-a**
  ```bash
  git pull <remote> <branch>
  ```
- **Preuzimanje promjena bez merge-a**
  ```bash
  git fetch <remote> <branch>
  ```

