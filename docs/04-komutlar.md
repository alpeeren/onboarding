### İçerik
1. [Git'e Giriş](01-git.md)
2. [Temel Git Kullanımı](02-kullanim.md)
3. [Git ile İşbirliği](03-isbirligi.md)
4. Komut Kılavuzu
    1. [Repository ve Branch Oluşturma](#4i-repository-ve-branch-oluşturma)
    2. [Staging ve Commit Oluşturma](#4ii-staging-ve-commit-oluşturma)
    3. [Remote ve İşbirliği](#4iii-remote-ve-i̇şbirliği)
---

# 4. Komut Kılavuzu

## 4.i. Repository ve Branch Oluşturma

##### Repository oluştur

```bash
$ git init
```

##### Yeni branch oluştur

```bash
$ git checkout -b "<branch adı>"
```

##### Farklı brancha geç

```bash
$ git checkout "<branch adı>"
```

##### Branchları gör

```bash
$ git branch
```

##### Branch sil

```bash
$ git branch -d "<branch adı>"
```

## 4.ii. Staging ve Commit Oluşturma

##### Stagelen*me*miş dosya değişikliklerini görüntüle

```bash
$ git diff
```

##### Değişiklik yapılmış bütün dosyaları stagele

```bash
$ git add -A
```

##### Belirtilen dosyayı stage'le

```bash
$ git add <dosya>
```

##### Staging durumunu görüntüle

```bash
$ git status
```

##### Stagelenmiş dosya değişikliklerini görüntüle

```bash
$ git diff --cached
```

##### Verilen mesaj ile commit oluştur

```bash
$ git commit -m "<mesaj>"
```

##### Commit tarihçesini görüntüle

```bash
$ git log
```

##### Verilen commiti geri al

```bash
$ git revert --no-edit "<commit kodu>"
```

## 4.iii. Remote ve İşbirliği

##### Verilen repositoryyi indir ve içine gir

```bash
$ git clone "git@github.com:<kullanıcı adı>/<repository>.git"
$ cd <repository>
```

##### Farklı bir forkun bağlantısını ekle

```bash
$ git remote add fork "git@github.com:<kullanıcı adı>/<repository>.git"
```

##### Remote bağlantıları görüntüle

```bash
$ git remote -v
```

##### Ana projeden değişiklikleri güncelle

```bash
$ git checkout main
$ git pull origin main
```

##### Commitleri forka yükle

```bash
$ git push fork <branch adı>
```

##### Commitleri doğrudan ana projeye yükle

> [!CAUTION]
> Bu komut yalnızca proje yöneticisi tarafından kullanılmalı.

```bash
$ git push origin <branch adı>
```

---

> [Ana sayfaya dön](https://github.com/aaltebigep/onboarding#readme)
