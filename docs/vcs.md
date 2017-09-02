# Kayıtları Saklamak İçin Yöntemler
İDS formatı üzerine aşağı yukarı her şey konuşulduğuna göre, ara ara değindiğim bu kayıtlar nasıl saklanacak? Konusuna derince değinmenin zamanı sonunda geldi...

Kayıtları saklamak için (ve hatta bu kayıtları oluşturmak için) bir çok farklı yöntem var ve kendinize en uygun gelenini seçmelisiniz.

## Kayıtları yazmak
İDS sırasında elinizde bir çok belge birikecek. Konferans kayıtlarından, kanunlara. Bunları dijital olarak ya da elle tutabilirsiniz, ancak elle tutulan kayıtların dijitale aktarılmasını tavsiye ediyoruz. Bu kayıtlar için bir çok yöntem vardır:

### Markdown (.md)
Markdown son derece kolayca kullanılabilen bir yazı dilidir. Dosyalarınızı yazdıktan sonra .md dosyaları halinde tutabilir ve dilerseniz pdf'e çevirebilirsiniz. Markdown yazmak için Atom isimli programı tavsiye ediyoruz. Bu programı internetten [şu](http://atom.io) adresten ve ya Debian'da `apt install atom` komutuyla indirip kurabilirsiniz.

Markdown hızla yazılır ve düşük yer kaplar. Şu an okuduğunuz belgelerin hepsi Markdown'la yazılmıştır.

### Microsoft Word Document (.docx)
Word Dosyaları endüstri standartı dosyalardır. Ancak kapladıkları yer Markdown'a göre çok daha fazladır ve tablo yapmak gibi özellikleri daha zorludur. Bununla beraber Word daha standarttır.

### Open Document Text (.odt)
Open Document Text formatının Word'den pek bir farkı yoktur. Ancak açık kaynaktır ve Libre Office ile Open Office'in standart formatıdır.

### Sonuç:
Format|Küçük Boyut|Hız|Evrensellik
------|------------|----|---------
Markdown| <center> :white_check_mark: |  :white_check_mark: | <center> :x:
Word | <center> :x: | <center> :x: | <center> :white_check_mark:
ODT | <center>:x: | :x: | <center>:x:

## Kayıtları Saklamak
İşin asıl çetrefilli kısmı, ne şekilde bir saklama yöntemi izlenmesi gerektiği hususundadır. Bu yöntemleri *basit* ve *karmaşık* olarak inceleyeceğiz.
Bize göre bütün kayıtlar herkes için açık ve okunabilir olmalıdır ki İDS'de bulunan fikirler yayılabilsinler.

### Basit Yöntemler
#### Google Drive & OneDrive
Google Drive ve OneDrive gibi bulut çözümleri, hem dosyalarınızı saklamanızı hem de onları düzenleyebilmenizi sağlar. Ancak bu iki sistem de Markdown desteklememektedir ve ücretsiz yer sınırı bulunması bir süre sonra Word dosyalarınızı saklamanızı güçleştirebilir ancak en az beş altı yıl bu sınır yüksek ihtimalle size yetecektir.
#### Dropbox
Dropbox dosyalarınızı düzenlemenize izin vermese de, PDF şeklinde saklama yolunu izlerseniz gidebileceğiniz en iyi yerlerden biridir.

### Karmaşık Yöntemler
#### Git
Git en basit karmaşık yöntemdir. Git için yapmanız gereken şey öncelikle uzak bir hesap açmaktır. Bu hesabı [GitHub](github.com), [Bitbucket](bitbucket.org) ya da [GitLab](gitlab.com)'dan açabilirsiniz ancak bu rehberde GitHub'ı inceleyeceğiz. Bununla beraber anlatılanların çoğu diğer sistemler için de geçerlidir.

GitHub hesabınızı açtıktan sonra, Create New Repository seçeneği ile herhangi bir lisans ya da readme yaratmadan *boş* bir depo açın.

Şimdi dilerseniz dosyalarınızı internetten ekleyebilirsiniz ancak daha doğrudan bir bağlantı istiyorsanız bunu bazı kodlarla yapmanızı tavsiye ederim, yani şöyle:

`NOT: Aynı zamanda bilgisayarınızda Git programı da yüklü olmalıdır. Aşağıdaki kodlar Linux ve Mac bilgisyarlar içindir`

```bash
# Eğer yüklü değilse git'i yükleyelim
# Linux (Debian) için:
sudo apt install git
# Mac (brew) için:
brew install git

# Şimdi Depomuzu kuralım
git init
git add "dosyalarınız" "boşlukla" "ayrılabilir"
git commit -m "herhangi bir mesaj"
git remote add origin reponun_rinki
git push origin master
```
varolan bir repoyu ise `git clone repo_linki` şeklinde indirebilirsiniz, ayrıca daha sonra güncellemeleri almak için `git pull` komutunu kullanabilirsiniz.

#### Mercurial
Mercurial Git benzeri bir versiyon kontrol sistemidir ancak bunun dışında yüklemenizi gerektirebilir, BitBucket tarafından desteklenen Mercurial ise GitHub'la aynı şekilde internetten kurulabilir, kodlarla ise şu şekilde kurulur:

```bash
# önce Merucrial'ı yükleyelim
# Linux (debian):
sudo apt install mercurial
# Mac (brew):
brew install mercurial

#şimdi repomuzu hazırlayalım
hg init
hg add "dosyalarınız"
hg commit -m "hernangi bir mesaj"
hg push reponun_linki
```
GitHub'da BitBucket'de Markdown desteklemektedir ancak sınırlı sayıda yer sunarlar. Markdown dosyaları küçük olduğundan buna takılma olasılığınız oldukça düşüktür.

Commit ile atılan mesajlar, kendi yüklediğiniz dosyaların niye yüklendiğini ve yapılan değişiklikleri not almanız içindir.

#### Sphinx
Eğer gerçekten canı sıkılan bir insansanız, kendi sunucunuz üzerinde dosyalarınızı ReStructeredText halinde Sphinx'le saklayabilirsiniz. readthedocs.org'un kullandığı bu formatı kendi makinenize yüklemek için [şu adrese](http://docs.readthedocs.io/en/latest/install.html) başvurabilirsiniz.

## Peki biz nasıl kayıtlarımızı saklıyoruz

Deneme kayıtları için BitBucket kullanıyoruz. Ancak İDS'nin normal versyonu başladığında kanunları GitHub'da saklayacağız. Git ve Markdown kullanıyoruz.

[Önceki sayfa](ic_tutarlilik.md)
