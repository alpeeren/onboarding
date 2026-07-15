### İçerik
1. [Git'e Giriş](01-git.md)
2. Temel Git Kullanımı
    1. [Git'in Kurulumu](#2i-gitin-kurulumu)
    2. [İlk Commit](#2ii-i̇lk-commit)
3. [Git ile İşbirliği](03-isbirligi.md)
---

# 2. Temel Git Kullanımı

## 2.i. Git'in Kurulumu

Bütün uygulamalarda olduğu gibi, Git'in kurulumu kullandığınız işletim sistemine göre değişecektir.
Bu yüzden bu bölümde Git'in kurulumuna dair çok fazla detaya inmeyeceğiz. Git'i [kendi sayfasından]
işletim sisteminize göre indirip kurmalısınız. Ancak çoğunuzun Windows kullandığını varsaydığımdan,
Windows kurulumu esnasında yapmanızı önerdiğim bazı değişiklikleri burada listeleyeceğim. Eğer farklı
bir işletim sistemi kullanıyorsanız ve emin olmadığınız bir şey varsa, GitHub'dan sorumlu TEBİGEP
üyesine danışabilirsiniz.

- Eğer Windows 11 veya daha yenisini kullanıyorsanız, bileşen seçme aşamasında `Add a Git Bash
Profile to Windows Terminal` (bilgisayarınızın diline göre değişebilir) seçeneğini aktive ediniz.
- Varsayılan editör seçme aşamasında kendi keyfinize göre bir editör seçiniz. **Eğer bilgisayarınızda
yoksa ve hâlihazırda bir editöre ihtiyacınız varsa**, oldukça popüler bir tercih olan [Visual Studio Code]'u
kurup Git kurulumuna tekrar başlayarak onu seçebilirsiniz. Eğer editör kurmak istemiyorsanız, `nano`yu
seçmeniz daha iyi olacaktır. Diğer seçenekleri pek fazla *önermem*.
- Ekstra ayarlarda `symbolic link`leri açmanızı tavsiye ederim.
- Git kurulduktan sonra her şeyin kullanılmaya hazır olduğundan emin olmak için bilgisayarınızı yeniden
başlatmayı deneyebilirsiniz.

## 2.ii. İlk Commit

Fikir paylaşımı ve araştırmanın kolay olması için Git'i metinsel ortamda kullanacağız. Bunun için Windows 11+
kullanıyorsanız `Windows Terminal` uygulamasını açıp `Git Bash` cinsi bir sekme açabilir, daha eski bir Windows
kullanıyorsanız `Git Bash` uygulamasını doğrudan kullanabilir, diğer işletim sistemlerinde ise hâlihazırda
kullandığınız terminal öykünücünüzü kullanabilirsiniz.

Git'in sizi tanıması için bazı ayarlar yapmamız gerekiyor. Terminalinizi açtıktan sonra, bu işlem için üç
komut kullanacağız. Aşağıdaki satırlarda `$` sembolünden sonraki metini terminalinize yazarak çalıştırın.
Unutmayın ki üç satırı ayrı ayrı çalıştırmanız gerekecek. Bu satırları doğru okuduğunuzdan, `user.name`'den
sonra kendi adınızı girdiğinizden, `user.email`'den sonraki kısımda girdiğiniz email adresinizin kendi adresiniz
olduğundan ve GitHub'a kayıt olduğunuz adres ile aynı olduğundan emin olun. **Bu işlemi yalnızca Git'i ilk
kullandığınızda yapmalısınız.**

```bash
$ git config --global user.name "<Adınız>"
$ git config --global user.email "<Mail Adresiniz>"
$ git config --global init.defaultBranch main
```

Şimdi bir repository oluşturarak başlayalım. İstediğiniz bir yerde bir dizin (klasör) oluşturun ve o
dizinde terminalinizi açın. Eğer Windows kullanıyosanız dizine sağ tıklayıp Terminal'i veya Git Bash'i
o dizinde açabilirsiniz. Daha sonra ise o klasörde repository'mizi başlatalım. **Bu komudu her repository
için bir kere yapmanız yeterli.**

```bash
$ git init
```

Bu komuttan sonra artık bahsi geçen dizininiz bir repository oldu. Tebrikler! Favori editörünüzü veya
dosya yöneticinizi kullanarak o dizinde bir dosya oluşturup o dosyaya bir şeyler yazabilirsiniz. Genelde
ilk dosyanız `README.md` olur ancak tabii ki bu opsiyonel. Dosyanıza bir şeyler yazıp kaydettiyseniz,
ilk commit'imizi oluşturabiliriz. Commit'i oluşturmadan önce, commit'te spesifik olarak hangi değişikliklerin
olacağını Git'e söylememiz gerekiyor, ve buna "***staging***" deniyor. Bunu `add` ile yapabiliriz. Aşağıdaki
komut otomatik olarak değiştirdiğiniz *bütün* dosyaları commit'e dahil edecektir. Eğer dosyaları tek tek eklemek
isterseniz, `-A` yerine dosyaların adını tek tek yazabilirsiniz, ancak buna çoğu zaman ihtiyacınız olmayacak.

```bash
$ git add -A
```

Şu anki staging durumunuzu görmek için şu komudu kullanabilirsiniz:

```bash
$ git status
```

Değişikliklerimiz hazır olduğuna göre commit'imizi yapalım. Her commit'in bir açıklaması olur. Örneğin
bu durumda `README ekle` gibi bir açıklamayla commit yapalım.

```bash
$ git commit -m "README ekle"
```

Commit'imiz bitti! Artık yaptığımız değişikliklerin bir kaydı var. Bulunduğunuz branch'taki commit'leri görmek
için aşağıdaki komudu kullanarak yaptığınız şeyi görüntüleyip mutlu olabilirsiniz.

```bash
$ git log
```

`log` ile baktığınız commit'lerde uzun bir yazı görebilirsiniz, örneğin `commit 3261534419236c06e3fa5e71894d417cbfccf5a1`.
Bu yazıda `commit`'ten sonraki şey o commit'in kodu. Eğer gerçekten sevmediğiniz veya pişman olduğunuz bir commit olursa,
aşağıdaki komutla o commit'i ve içerdiği değişiklikleri geri alabilirsiniz! Git bu işe yarıyor sonuçta!

```bash
$ git revert --no-edit 3261534419236c06e3fa5e71894d417cbfccf5a1
```

Git ile ilgili aşağı yukarı bilmeniz gereken komutların hepsi bu aslında, geri kalanı biraz daha karmaşık
işler için kullanılacak, ve onları ileriki bölümlerde göreceğiz. Ancak elbette bunları da ezberlemenize gerek yok.
Bu oryantasyonun son bölümünde Git komutlarına dair notlar yer alacak.

Lütfen sonraki bölüme geçmeden önce bu kısmı anladığınızdan emin olun, ve eğer yapabiliyorsanız birden fazla commit
ekleyip `git log` ile bakarak değişikliklerin nasıl depolandığını anlamaya çalışın.

---

> [Sonraki bölüme git](03-isbirligi.md)

[kendi sayfasından]: https://git-scm.com/install/windows
[Visual Studio Code]: https://code.visualstudio.com/download
