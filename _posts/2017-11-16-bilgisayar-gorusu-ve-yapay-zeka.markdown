---
layout: post
title: "[Turkish] Bilgisayar Görüsünün ve Yapay Zekanın Durumu: Daha Çok, Çok Yolumuz Var.* "
categories: general
comments: true
permalink: "/bilgisayar-gorusu-ve-yapay-zeka.html"
---



![image](/assets/images/obama.png)

_Bu yazı Andrej Karpathy'nin izni ile teknik kısımları sadeleştirilerek Türkçeye çevrilmiştir._

Eğlenceli bir resim.

Fakat beni Yapay Zekanın ve Bilgisayar Görüsünün (Computer Vision) gidişatı hakkında üzen örneklerden bir tanesi. Bir bilgisayarın bu resmi sizin veya benim gibi anlamasını sağlamak için neler gerekir ki? Sizi, bu resmi anlamak için gereken her bir bilgi parçası hakkında (tıpkı bir yazılımın yapacağı gibi[1]) tek tek detaylarına inerek düşünmeye davet ediyorum. İşte benim denemem:

- Resimde koridorda bekleyen pek çok kişi olduğunu görüyorsunuz.

- Resimde 3 tane ayna olduğunu ve bazı insanların farklı bakış açılarından "sahte" kopyalar olduklarını fark ediyorsunuz.

- Yüzünü oluşturan birkaç pikselden Obama'yı tanıyorsunuz. Takım elbise giymesi ve etrafının da takım elbiseli adamlarla dolu olması size yardımcı oluyor.

- Tartı, arka planla karışmış birkaç beyaz piksel kapladığı halde tartının üzerinde duran bir adam olduğunu fark ediyorsunuz. Bunu anlamak için tartının üstündeki adamın pozunu ve insanların objelerle nasıl etkileşime geçtiğine dair bilginizi kullandınız.

- Obama'nın, ayağını tartının birazcık üzerine koyduğunu fark ediyorsunuz. Kullandığım dile dikkat edin: Sahnenin 3 boyutlu yapısını göz önünde bulundurarak değerlendiriyorum, bacağın resmin iki boyutlu koordinat düzlemindeki pozisyonunu düşünerek değil.

- Obama tartıya yaslanıyor, böylece ona kuvvet uyguluyor ve tartı kendisine uygulanan kuvveti ölçüyor. Fiziğin bu şekilde işlediğini bildiğiniz için bu hareket sebebiyle tartıdaki değerin olması gerekenden fazla çıkacağını öngörüyorsunuz...

- Kilosunu ölçmeye çalışan adam, Obama'nın yaptığı şeyden haberdar değil. Bunu çıkarsadınız çünkü nasıl poz verdiğini görüyorsunuz. Bir insanın görüş alanının kısıtlı olduğunu da biliyorsunuz ve tartıdaki adamın, bu hafif dokunuşu fark edemeyeceğine karar veriyorsunuz.

- Resimdeki adamın tartıdaki değeri okuduğunun ve beklediğinden fazla çıkan değerden dolayı tedirgin olacağının farkındasınız. Çünkü insanların kiloları konusunda takıntılı olduklarını biliyorsunuz. Başka bir deyişle, bu fotoğraf çekildikten saniyeler sonra ortaya çıkacak durumun etkileri hakkında özellikle de insanların kafasında oluşacak düşüncelere ilişkin akıl yürütüyorsunuz. Ayrıca fotoğraftaki insanların hangi bilgilere sahip olabileceği üzerine de akıl yürütüyorsunuz.

- Arkada, tartıdaki adamda az sonra oluşacak kafa karışıklığını komik bulan insanlar var. Diğer bir deyişle, insanların ruh halleri üzerine akıl yürütmekle kalmıyor aynı zamanda onların başkalarının ruh halleri hakkındaki düşünceleri üzerine de akıl yürütüyorsunuz. Bu iş ürkütücü bir meta halini almaya başladı...

- Son olarak, buradaki failin Başkan Obama olması bu resmi belki daha da komik kılıyor. Hangi hareketin hangi sıklıkla yapılmasının kişinin sosyal statüsüne ve kimliğine nasıl bağlı olduğuna dair bir yargıya varıyorsunuz.

Daha devam edebilirim, fakat burada önemli olan yarım saniye bakıp güldüğünüz bu resmi anlamak için çok büyük miktarda bilgiyi kullandığınızı fark etmeniz. Sahnenin 3 boyutlu yapısı hakkındaki bilgi, ayna gibi kafa karıştıran görsel nesneler, insanların kimlikleri, sağlarlıklar[2] ve insanların nesnelerle olan etkileşimleri, fizik bilimi (bir alet nasıl çalışır, adımın basılıyor olması ve etkileri), insanlar, onların kiloları hakkında güvensiz olma eğilimleri... Konuyu tartıdaki adamın bakış açısından analiz ettiniz, nelerin farkında olup neleri bilmesinin mümkün olduğuna ilişkin bir yargıya vardınız. Başkaları hakkında akıl yürüten insanlar hakkında akıl yürüttünüz.[3] Ayrıca sahnenin dinamikleri üzerinde düşündünüz ve birkaç saniye sonra sahnede neler olacağına ilişkin tahminde bulundunuz. Oradaki insanlara ait düşüncelerin seyri hakkında ve böyle özel bir statüye sahip bir kişinin bu hareketi yapma ihtimali üzerine akıl yürüttünüz. Bir şekilde bütün bunlar bir araya geldi ve sahnenin örgüsü kurulmuş oldu.

Bütün bu çıkarımların 2 boyutlu kırmızı, yeşil ve mavi değerlerinden oluşan bir dizgeye kısa bir bakış atarak yapılabiliyor olduğunu düşünmek inanılması zor bir şey. Temel problem ise piksel değerlerinin sadece buz dağının görünen yüzü olması. Bütün bir şekli ve onun büyüklüğünü önceki bilgilerimizden elde etmemiz karşımızdaki en büyük problem. Sahne hakkında benim yaptığım gibi akıl yürütebilen bir algoritmayı yazmaya nereden başlayabilirim ki? Bütün bunları bir araya getirecek çıkarım algoritmasını yazmayı bir kenara bırakın, bu çıkarımlar için gerekli veriyi (örneğin bir tartı nasıl çalışır?) toplamaya nereden başlayacağız? Bilgisayara böyle bir olanağı tanımak için ne yapabiliriz ki? Poz tahmini, hareket algılama vb. üzerine pek çok çalışma var fakat bunların hepsi spesifik ve birbirinden bağımsız yarım işler. Bunu söylemekten nefret ediyorum ama böyle görevleri ve o noktaya nasıl varacağımızı düşündüğümüzde Bilgisayar Görüsünün ve Yapay Zekanın durumu acınası bir halde. Önümüzde uzun, belirsiz ve muğlak bir yolun olduğunu itiraf etmek zorundayız.

Bütün yapmamız gerekenin resimlerden, videolardan, metinlerden daha fazla veri toplamak ve daha zekice öğrenme algoritmaları geliştirmek olduğunu söyleyen argümanlar görüyorum. Fakat bence, bu resimdeki gibi örnekler bize yapbozun pek çok önemli parçasının eksik olduğunu ve temel problemin en az doğru veriyi doğru şekilde çıkarımlara tabi tutmak kadar büyük olduğunu gösteriyor.

Problemin karmaşıklığını ve geniş ölçeğini göz önünde bulundurduğumuzda, böyle sahneleri algılayabilecek bilgisayarlar üretmenin bir yolu olabilir: Bizim yılların birikimiyle deneyimlerimizi inşa etmemize benzer şekilde onların da dünyayla etkileşim kurmaları. Nasıl bir şey olduğunu geriye dönüp düşündüğümde zar zor hatırladığım büyülü bir aktif öğrenme/çıkarım mekanizmasına onların da ihtiyaçları var.

Her neyse, o noktaya çok çok uzağız ve bu benim canımı sıkıyor: Önümüzde ne var? Belki de bunları bırakıp girişimcilikle uğraşmalıyım. Aklımda gerçekten hoş bir yerel-sosyal iPhone uygulaması fikri var...

Çeviri: Ömer Kırbıyık

Link:

[http://karpathy.github.io/2012/10/22/state-of-computer-vision/](https://www.google.com/url?q=http://karpathy.github.io/2012/10/22/state-of-computer-vision/&sa=D&ust=1497112293129000&usg=AFQjCNFHBZ69cZxsmg-_yGLBH5eIBiFzqg)

---

[1] Çevirmenin notu.

[2] Bir aksiyonun özne açısından nesneye uygun olması ya da olmaması. Mesela bir bardak bir insan tarafından tutulabilir veya kırılabilir fakat bir bardakla tahtaya yazı yazılamaz. İlk ikisi nesnenin algılanabilir sağlarlığına birer örnektir. Bir bilgisayar oyununu düşünün: Bir odadaki televizyonu açıp kapatabilmeniz genellikle mümkündür fakat televizyonu masa olarak kullanamazsınız.

[3] You’ve reasoned about people reasoning about people.
