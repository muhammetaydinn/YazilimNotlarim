echo %cd% bulunan klasoru gösteriir
macos ve linuxta pwd bulunan klasoru gösteriir

Satırın neresinde olursanız olun bir alt satıra geçmek istediğinizde CTRL + ENTER kısayolunu kullanabilirsiniz.

snippet configure ederek sürekli kullanacağın fonksiyonların shortcut ını yapabiirsin

Bu ayarların bütününü görüntülemek için:

$ git config --list
Bu hatanın çözümü için aşağıdaki komutu kullanabilirsiniz.

$ git config core.autocrlf true
git rm
Staged ortamına eklenmiş bir dosyanın takibinin bırakılması yani untracked (izlenmeyen) hale getirilmesi sağlayan komuttur.

$ git rm  --cached <dosya veya klasor_name>
Dosyayı klasörden silmek istiyorsak eğer, aşağıdaki komutu kullanılırız.

$ git rm <dosya veya klasor_name>
Projedeki commit geçmişini görüntülememizi sağlar. Bütün commit'ler, id'si, yazarı, tarihi ve mesajı ile beraber listelenir.

$ git log
git branch
Local veya remote repository üzerinde yeni bir branch (dal) eklemek, silmek veya listelemek için kullanılır.

Projenize yeni bir branch eklemek için;

$ git branch <branch_name>
*Tüm uzak ve yerel branch'lari listelemek için;

$ git branch -a
Bir branch'ı silmek için;

$ git branch -d <branch_name>
git checkout
Branch’ler arası veya commit'ler arası geçiş yapmak istediğimizde kullanılır.

Mevcutta var olan branch'a geçiş yapmak için;

$ git checkout <branch_name>
Yeni bir branch oluşturup, bu branch'a geçiş yapmak için;

$ git checkout -b <branch_name>
git merge
Başka bir branch'da olan değişiklikleri, bulunduğumuz branch ile birleştirmek istediğimizde kullanılır.

$ git merge <branch_name>
 "A" (1) (added)

 "U" (2) (untracked) 

"M" (1) (modified) 

