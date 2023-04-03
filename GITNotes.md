# **Versiyon Kontrol Sistemi(GIT) Nedir?** 
* Bir döküman (yazılım projesi, ofis belgesi vb.) üzerinde yaptığınız degişiklikleri adım adım izleyen, istediğinizde kayıt eden ve isterseniz bunu internet üzerindeki bir bilgisayarda veya yerel bir cihazda (respository / repo / depo) saklamanızı ve yönetmenizi sağlayan bir sistemdir.

* Gite 3 farklı yoldan erişim sağlayabiliriz.

1. Projeye Desktop üzerinde sağ tıklayıp Git Bash Üzerinden
2. Vs Code Üzerinde Terminal kullanarak Git kullanma
3. Vs Code üzerinde terminall kullanmadan GIT Kullanma

* Git ,projelerimizi uzak sunucularda güvenle depolamamızı sağlar.Bu uzak sunucular Github gibi hosting görevi gören sunucular olabilir.

## Git komutları

**git init**:Bir proje git ile açıldığında git komutlarının çalışabilmesi için gerekli olan ve ilk yazılması gereken komuttur.(***initialize***)

**git add**:Herhangi bir dosyayı veya klasörü takip etmek için bu komut kullanılır.Dosya staged ortamına gönderilir.

* git add . komutu ile tüm dosyalar takip edilir.

**git commit**:Projeyi onaylamak ve snapshotunu(anlık durum görüntüsünü) almak için kullanırız.Staged ortamına alınan dosyaları Local Repository(Yerel Depo)'ye gönderir.

* commit işlemi projede yapılan değişiklikleri projenin geçmişine eklemeyi sağlar.

**git commit -m 'First Commit'**: Takip edilen dosya için açıklama yapılabilir.(***-m = message***)

**git status**:Projede ne gibi değişiklikler olduğunu görmemizi sağlar.

**git push**: Projeyi uzak bilgisayara,sunucuya(github) göndermemizi sağlar.

**git pull**:Uzak bilgisayardan,sunucudan projeyi çekmemizi,geri getirmemizi sağlar.

**git clone**:Projeyi klonlamamızı,kopyalamamızı sağlar.(cmd ekranından)

**git checkout**:Proje içerisinde birden fazla kişi çalışıyorsa bu komut sayesinde branchimize geçiş yapabiliriz.Ayrıeten commitler arası geçiş de yapabiliriz

**Branch**:Bir projede birden fazla kişinin çalışması durumunda her kişinin projeye bağlı olarak kendi alanlarında(branchlarında) çalışması gerekir.Daha sonra branchlerde çalışan her bir kişi uygun kodları test ederek ana projeye aktarabilir.

**git checkout branchAdi**:Branch'e geçiş yap.

**git checkout commitID**:Commit'e geçiş yap.(*git log komutuyla commitID görülebilir*).

**git rm**:Dosyaları veya klasörleri silmek için kullanılır.

**git rm --cached dosyaAdi**:git add komutuyla takip edilen dosya takipten çıkılır. Bu komutla aynı işlevi **git restore --staged dosyaAdi** komutu da görür.

**git diff**:Bu komut ile en son yapılan commit işleminden sonra gerçekleşen tüm değişiklikler gösterilir.

**git log**:Projede yapılan commitlerin listesi görüntülenir.

**NOT**:Bir dosya üzerinde commit işlemi yapmadan önce mutlaka tekrar takibe alınmalıdır.Çünkü birden fazla dosya takibe alınmış olabilir.Commitleme işlemini istediğimiz dosya üzerinde yapmak istiyorsak önce onu takibe almalıyız.

**git restore dosyaAdi**:Değişklik yapılan dosya üzerindeki değişikliği geri almamızı sağlar(commitleme işleminden sonra)

**git config --list**:Config ayarlarının tamamı görüntülenir.

**git branch**:Yeni bir branch eklemek,silmek veya listelemek için kullanılır.

**git commit --amend** komutuyla son yapılan commit işleminin açıklaması değiştirilebilir.

*:Q* = Sayfadan çık

*** 

* Projede versiyonlanmaması gereken dosyalar vardır.Bunlar projede tutulmamalıdır.

**.gitignore** dosyasıyla bu versiyonlanmaması gereken dosyaları belirtebiliriz.Bu dosyalar şunlar olabilir:

- Görseller
- Videolar
- Logolar
- Paket yöneticisi ile kurulmuş dosyalar
> .gitignore dosyası proje içerisinde oluşturulur.


* Projemle ilgili denemek istediğim bir şeyler olabilir.Bu yapacağım deneyin diğer dosyaları,mevcut proje yapısını değiştirmesini istemiyorum.*Bunun için yeni branch oluşturabilirim.*

**git branch branchName** ile yeni bir branch oluşturup üzerinde çalışabiliriz.

* Oluşturduğum branch üzerinde çalıştığımda ordaki değişiklikler o branchte kalacaktır.Tekrar eski branche geri döndüğümde diğer branchte yaptığım değişikliklerin kaydedilmediğini göreceğim.Bu ilerde projeler üzerinde deneme yanılma çalışmaları yapmak istediğimde ana projemin değişmemesini,projemin yaptığım bu değişikliklerden etkilenmemesini sağlayacak.

**git checkout brancName** ile branchler arası geçiş yapılabilir.

* Yapılan bir commit işlemini geri almak istediğimizde **git revert commitID** komutunu kullanabiliriz.

* Branchlerde yaptığımız değişiklikleri ana branchimizde birleştirmek istiyorsak ana branche(master) gidip birleştirmek istediğimiz branchin adını komutun yanına yazıyoruz: **git merge brancName**

* Branchler takımlar halinde bir proje üzerinde çalışıldığında kullanılabilir.Herkes kendine ayrı bir branch açıp o branch üzerinde işlemini yapabilir.Daha sonra branchler ana branchte birleştirilir ve proje ortaya çıkmış olur veya bireysel olarak proje üzerinde denemeler yapmak istiyorsak da branch kullanabiliriz.

* GIT'le ilgili daha detaylı bilgilere [GIT'in kendi sitesinden](https://git-scm.com/) ulaşabilirsiniz.

## Github

* Create repository diyip söylenilen adımları uygulayarak proje Githuba aktarılabilir.main yerine master branchinde de çalışılabilir.git branch -M main:Bu komut master branchinin adını main olarak değiştiriyor.Zorunlu değildir.Direkt remote ile origin bağlantısını ekleyip(git remote add origin remoteBaglantisi)(bu işlemi Githubtan copy paste ile kolayca yapabiliriz.) bunu push edebiliriz(git push -u master).

* READme dosyasının eklenmesi başka insanlara rehber olması açısından önemlidir.READme dosyasında proje hakkında detaylı bilgiler verilebilir.(*READme dosyası ile ilgili detaylı bilgiler READme.md dosyasında mevcuttur*)

* Githubta Proje dosyaları üzerinde değişiklik yapabiliriz.Düzenle kısmında proje dosyası üzerindeki değişikliği yaptıktan sonra alt kısımda commit açıklamasını gireriz.Dilersek commite açıklama da ekleyebiliriz.Bu commit açıklamasını "git log" kısmından görebiliriz.Daha sonra değişikliklerin vsCode üzerinde de uygulanması için terminal ekranına gidip "git pull" komutunu çalıştırırız.Aynı şekilde vsCode'da proje üzerinde yaptığımız değişikliği Githubta görmek istiyorsak "git push" komutunu terminalde çalıştırabiliriz.

* Başkaları Githubta projemiz üzerinde çalışıyor olabilir.Biz bu değişiklikleri vsCodeumuzda görmek istiyorsak git pull komutunu çalıştırırız.

* Terminal ekranından git clone remoteBağlantısı komutu ile repomuzu pcmize aktarabiliriz.(Code kısmından)Veya direkt projeyi indirebiliriz.clone ile projemizi başka bir pcde açabiliriz.

* Githuba alternatif olarak Gitlab da kullanılabilir.

* GIT'i öğrenmek Githubu öğrenmekten daha önemlidir.Projelere READme ve gitignore dosyalarının eklenmesi önemlidir.

* READme dosyasının markdown ile etkili bir şekilde doldurulması önemlidir.

* rm .git ile mevcut bir proje üzerindeki GIT akışını tamamen silebiliriz.

* Aşağıdaki sıra ile vsCode üzerinden projeyi Githuba aktarabilirsin.tabii önce Github üzerinden "create a new repository" seçeneğine tıklıyoruz.

```GIT
git remote add origin https://github.com/alper-polat/deneme123.git
git branch -M main
git push -u origin main
```