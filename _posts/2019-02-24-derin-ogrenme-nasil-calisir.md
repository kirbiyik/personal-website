---
layout: post
title:  "[Turkish] Derin Öğrenme Nasıl Çalışır?"
categories: general
comments: true
permalink: "/derin-ogrenme-nasil-calisir"


---
**NOT: Bu yazı, amacı ve hedef kitlesi nedeniyle, matematiksel bir dilden uzak ve pek çok teknik detay atlanarak yazılmıştır. Temel amaç okuyucuya sezgisel bir anlayış inşa etmektir.**

---

Bilinç problemi çok uzun zamandır felsefe ve bilimi peşinden sürüklemeyi başarıyor. Kimine göre metafiziğin son kalesi, kimine göre bir yanılsamadan ibaret olan bilinç hakkında emin olduğumuz tek bir şey var, o da bilinç için çoğunluğu tatmin eden bir açıklamaya sahip olmadığımız gerçeği. Bilincin doğasına dair araştırma sahası içerisinde yer alan yapay bir bilincin üretilip üretilemeyeceği sorusu etrafında şekillenen çalışmalar, bu araştırma sahasının tümüne ışık tutacak çok değerli bilgiler elde etme fırsatını bizlere sunmaktadır. Dolayısıyla yapay zekâ çalışmaları hem bilincin bilgisine dair önemi ile hem de endüstriyel anlamda yaygın uygulamaları ile günümüzde oldukça ilgi çeken bir çalışma alanı konumunda. Pek çok yapay zekâ araştırmacısının 2012 yılından beri odaklandığı derin öğrenme yöntemi görece sessizce ilerleyen çalışmaları kış uykusundan uyandırdı ve işleri toplu konut reklamlarında dahi yapay zekâ kavramının kullanılması boyutuna kadar getirdi.

Öte yandan yapay zekânın bu denli popüler olması ve yapısı itibariyle spekülasyonlara müsait olması pek çok sorunu ortaya çıkarıyor. Heyecan verici sonuçları nedeniyle insanlar yapay zekâ çalışmalarının da herhangi bir mühendislik problemi gibi belirli bir modelle çözülmeye çalışılan gelişime açık ve muhtaç bir yapıda olduğunu unutup felaket senaryoları üretebiliyorlar ya da gerçekçi olmayan beklentilere girebiliyorlar. Yapay zekâ fanusunu bir nebze de olsa açmak amacıyla bu yazıda derin öğrenmenin temel işleyiş şekli teknik detaylar izole edilerek bir örnek üzerinden sezgisel düzlemde incelenecektir. Böylece matematiksel yoğunluğu nedeniyle güncel yapay zekâ yöntemlerine mesafeli duran felsefe, psikoloji, sinirbilim, dilbilim ve bilişsel bilim gibi yapay zekâ ile dolaylı yoldan ilgili disiplinlere mensup araştırmacıların da konu hakkında fikir edinmesi amaçlanmaktadır. 


## Yapay Zekâ, Yapay Öğrenme ve Derin Öğrenme Arasındaki Fark 

Bir bilgisayar bilimleri disiplini olarak yapay zekâ [artificial intelligence], zeki bir canlıdan beklenecek davranış ya da muhakeme yeteneğini bilgisayarlar ile gerçekleştirebilme yetisidir. Yapay öğrenme [machine learning] ise yapay zekânın alt dalıdır ve programın mevcut veri üzerinden bir takım çıkarımlar yaparak sorunu bir optimizasyon problemi haline getirip ilerlemesi amacını güder. Mesela bütün kombinasyonları göz önüne alarak her durum için ne yapılması gerektiğini tek tek kod hafızasında bulunduran bir satranç programı bir yapay zekâ çalışması örneğidir fakat yapay öğrenme örneği değildir. Bir problemin yapay öğrenme çerçevesinde çözülmesi için programcının tüm detayları kodlamasına gerek kalmadan programın gerekli bilgileri veri üzerinden çıkarabilmesi beklenir. Derin öğrenme [deep learning] de yapay öğrenmenin daha az müdahale gerektiren fakat veriye daha çok ihtiyacı olan özelleşmiş bir alt dalıdır.

## Derin Öğrenme Yeni Bir Çalışma Alanı mı?

Yapay Sinir Ağları prensipleri itibariyle yeni ortaya çıkmış bir çalışma alanı değildir. McCulloch ve Pitts 1943’te dönemin nöroloji bilgisine dayanarak bir takım modeller hazırladılar[1]. 1954 yılında IBM’de araştırmacı bir grup McGill Üniversitesindeki nörobilimcilerle ortak çalışmalar yürüterek günümüze dek uzanacak multidisipliner bir beraberliğin ilk adımlarını attılar.[2] 1969’da ise Marvin Minsky ve Seymour Papert, Perceptrons[3] isimli kitaplarında derin katmanlı modellere geçilmesi için henüz erken olduğunu yazdı ve onların bu alandaki otorite konumunda olmaları diğer insanların araştırma faaliyetlerinin de başka yönlere çevrilmesine sebebiyet verdi.

Günümüzde ise artan hesaplama kapasitesi ve çeşitli teknik ilerlemeler nedeniyle bu çalışmalarda tekrar canlanma yaşanıyor. Derin öğrenme imaj, dil, ses ve daha pek çok uygulama alanında en etkili yöntemlerden biridir ve bu yöntem kolay kolay rüzgarını kaybedeceğe de benzemiyor. 

## Derin Öğrenme Beyin Gibi mi Çalışır?

<figure style="text-align:center" >
    <img src="assets/images/derin-ogrenme-nasil-calisir/1.png" style=" display:block;margin:auto;" height="250px">
    <figcaption>Şekil 1</figcaption>
</figure>

Yapay sinir ağları modellerinde temel fikir sinaptik bağların güçlerinin w ile gösterilen değişken parametreler ile tutulması ve bu parametreleri veriyi işledikçe değiştirerek daha iyi bir temsilin sağlanmasıdır. Hesaplamada kullanılan modelde yapay sinir ağları çok katmanlı olduğu için derin öğrenme olarak adlandırılır. Matematiksel modelde bir nörona gelen her x kendi parametresi w ile çarpılır ardından o nörona özgü bir b sabiti ile toplanır. Daha sonra ilgili nöronun belli bir aktivasyon değerini aşıp aşmadığına bakılır. Matematiksel modelde nöronların ateşlenme zamanları göz ardı edilerek sadece ateşlenme frekansları dikkate alınır. Nöronların ateşlenme frekansları normal hesaplanan çıktının aktivasyon fonksiyonundan* geçirilmesiyle -değerinin değiştirilmesiyle- modellenir daha sonra bu sayı bir sonraki bağlantıya iletilir. Aktivasyon fonksiyonu aynı zamanda aktivasyon değerinin aşılıp aşılmadığını da dolaylı olarak kontrol eder. Bu bilgiler ışığında biyolojik model ile matematiksel model arasında ilişkiler kurmak elbette mümkündür fakat bu benzerlik iddiasına pek çok itiraz da mevcuttur. Biyolojik modeller elbette bu kadar basit değiller ve çok farklı varyasyonları mevcut. Bunun gerçek anlamda bir benzerlik mi yoksa bir imitasyon mu olduğuna dair tartışmalar sürmekle birlikte bu konu okuyucunun takdirine bırakılmıştır[4, 5].

## Bir Uygulama Örneği

İmajlar üzerinden kanser olup olmadığını tespit edebilen, bir insanın sesini taklit edebilen, başarılı ölçüde çeviri yapabilen ve gazetelerde hatta reklamlarda yapay zekâ kelimesini duymamıza yol açan derin öğrenme tekniğinin aslında görece basit bir çalışma şekli var. Gelişmiş yapay sinir ağı mimarilerini ve matematiksel yoğunluğu olan kısmını arka planda bırakarak bir örnek üzerinden derin öğrenmenin çalışma prensiplerini inceleyelim. El yazısı rakamların olduğu ve her bir resmin yalnızca bir rakam içerdiği MNIST[6] veri seti üzerinden bir örnekle başlayalım. 

28x28 piksel çözünürlükte olan bu resimler yalnızca siyah ve beyaz renklere sahip olduğu için her bir piksel 0 ile 255 arasında değişen sayılar ile temsil edilir. Bir pikselin değer olarak 0’a sahip olması onun tamamen siyah olmasını belirtirken 255 olması ise tamamen beyaz olduğu anlamına gelir. Aradaki geçişler ise ton farklılıklarını yansıtır. Eğer renkli bir resim ile uğraşıyor olsaydık her piksel kırmızı, yeşil ve mavi için ayrı ayrı 0 ve 255 arasında değişen bir değer ile temsil edilecekti. Örnek için Şekil 2’ye bakınız. 

<figure style="text-align:center" >
    <img src="assets/images/derin-ogrenme-nasil-calisir/2.png" style=" display:block;margin:auto;" height="300px">
    <figcaption>Şekil 2</figcaption>
</figure>

Artık elimizdeki görseli sayısal değerler bütününe çevirdiğimize göre yapay sinir ağı modelinin resimlere neler yaptığına göz atmaya başlayabiliriz. Şekil 3’te yuvarlak ile gösterilen her bir nöron kendisine gelen girdiyi ve girdiyle bağlantılarına bağlı olan ile bir sayı değerini, aktivasyon değeri de denebilir, tutmaktadır. Nöronlar arasındaki bağların görüldüğü üzere belirli kuvvetleri var. Bu kuvvetlerin kümesi ve nöronlara ait sabitler modelin parametreleri olarak adlandırılıyor. Modelin parametrelerine başta rastgele değerler atanıyor çünkü bu kadar yüksek boyutlarda çalışırken iyi sonuç verecek değerleri tahmin etmek mümkün değil. Aslında modelin yeni veri geldikçe öğrenmesini, bir röntgen filminde anomali olduğunu tahmin etmesini ya da çeviri yaparken hangi kelimeyi seçeceğine karar vermesini sağlayan şey bu parametreler bütünü. Bu parametreler her gelen yeni resimle birlikte güncelleniyor ve model yavaş yavaş ulaşması gereken noktaya ilerliyor. 


<figure style="text-align:center" >
    <img src="assets/images/derin-ogrenme-nasil-calisir/3.png" style=" display:block;margin:auto;" height="400px">
    <figcaption>Şekil 3</figcaption>
</figure>


Şimdi gösterimin kolaylığı açısından bütün resmin sadece 1 pikselden oluştuğunu, o pikselin değerinin bir tam sayı olduğunu düşünelim. Şekil 4’teki tablodaki gibi bir veri olduğunu hayal edip, verilen resimde lezyon olup olmadığını anlayan küçük bir yapay sinir ağı inşa edelim.

<figure style="text-align:center" >
    <img src="assets/images/derin-ogrenme-nasil-calisir/4.png" style=" display:block;margin:auto;" height="150px">
    <figcaption>Şekil 4</figcaption>
</figure>


Lezyonun varlığı ya da yokluğu açısından 2 durum söz konusu olduğu için son katmana 2 nöron koyduk. Bu nöronlardan eğer yukarıdakinin değeri yüksekse lezyon var aşağıdakinin yüksekse lezyon yok şeklinde modelleyeceğiz.


 Model parametreleri (nöronların bağlantılarının güçleri ve sabitler) ilk başta rastgele olarak başlatılır (Şekil 5).

Bağlantı Ağırlıkları = [{3,-1},{3,3},{2,1}]

Sabitler = [{7,8},{9},{10,11}]

 <figure style="text-align:center" >
    <img src="assets/images/derin-ogrenme-nasil-calisir/5.png" style=" display:block;margin:auto;" height="300px">
    <figcaption>Şekil 5</figcaption>
</figure>

Piksel değeri 8 olan imaj bütün nöronlardan geçtiğinde
Şekil 6 elde edilir.

<figure style="text-align:center" >
    <img src="assets/images/derin-ogrenme-nasil-calisir/6.png" style=" display:block;margin:auto;" height="300px">
    <figcaption>Şekil 6</figcaption>
</figure>

Başlangıçta 8 piksel değerine sahip veriyi girdiğimiz için modelimizden lezyon yok çıktısını bekliyorduk. Ancak sonuçta lezyon var çıktısını okuduğumuz nöron daha büyük değere sahip olduğu için modelimiz yanlış bir sınıflandırma yaptı. Modelin veriye göre parametrelerini güncellemeyi öğrenmesi için bir ceza fonksiyonu tanımlayacağız. Modelden ceza fonksiyonunu minimize etmesini isteyeceğiz dolayısıyla problemimiz artık bir optimizasyon problemi haline gelecek. Örnek bir ceza fonksiyonunu şöyle tanımlayabiliriz: 

Ceza = Yanlış olan sınıfın skoru / Doğru olan sınıfın skoru

Böylece modeli doğru olan sınıfın skorunu yükseltip diğer sınıfın skorunu düşürmesi için teşvik etmiş olacağız. Gerçek uygulamalarda matematiksel açıdan kullanışlı olması için daha farklı bir fonksiyon kullanılıyor olsa da temel mantık bu şekildedir. 

Öğrenmenin gerçekleştiği belki de en önemli aşama ise parametrelerin yani nöronlar arasındaki bağlantıların ve sabitlerin değerlerinin değiştiği aşamadır. Burada ceza fonksiyonunu kullanarak modelin hesaplama grafiği üzerinde türev almamızı sağlayan Geri Yayılım Algoritması[7] devreye giriyor. 

Geri Yayılım Algoritmasının çalışmasının ardından parametrelerin güncellendiğini varsayalım. Şimdi piksel değeri 13 olan imaj ile aynı işlemler tekrar edecek ve Şekil 7’deki durum oluşacak.


<figure style="text-align:center" >
    <img src="assets/images/derin-ogrenme-nasil-calisir/7.png" style=" display:block;margin:auto;" height="300px">
    <figcaption>Şekil 7</figcaption>
</figure>

Yine aynı şekilde ceza fonksiyonuna buradaki hata payını ekleyip Geri Yayılım Algoritması ile nöronlar arasındaki bağlantıları güncelliyoruz. Şimdi piksel değeri 6 olan imajı işleyelim.(Şekil 8) Şu an elimizdeki ağırlık ve sabitleri kullanarak veri setimizdeki tüm noktalarda doğru tahmin yapabilen bir model oluşturduk. Şu ana kadar lezyon olup olmadığı bilinen resimlerle modelin parametrelerini güncelledik. Bu aşamaya modelin eğitilmesi adı veriliyor. Daha sonra elimizdeki yeni bir imajda lezyon olup olmadığını tahmin etmek için piksel değerini elde edip, modelden geçirip sonucu aynı şekilde okuyacağız. 


<figure style="text-align:center" >
    <img src="assets/images/derin-ogrenme-nasil-calisir/8.png" style=" display:block;margin:auto;" height="300px">
    <figcaption>Şekil 8</figcaption>
</figure>

Bu anlatımdan fark edileceği üzere temel olarak yapay sinir ağlarıyla yapmaya çalıştığımız belli girdileri verdiğimizde belli çıktıları verecek karışık bir fonksiyon bulmak. Bunu yapmak için girdiyi belli sayılarla çarpıp belli sayılarla toplayan bir model hazırlıyoruz ve daha sonra bu sayıları güncelliyoruz. Elimizdeki veri setine bakarak daha basit bir formül bulmak da mümkündü fakat veri seti çok büyük olduğunda -imajların da sadece 1 değerden değil milyonlarca değerden oluştuğunu düşünürsek- tüm veriyi kapsayacak basit bir formül oluşturmanın kolay bir yolu yok. Fakat derin öğrenme yöntemi ile on binlerce resimden oluşan bir veri setini daha büyük bir model yani daha fazla parametre kullanarak yine bu şekilde tahmin edebilen bir sistem tasarlayabiliriz. Dikkat edilmesi gereken bir nokta ise modelin eğitimini model verinin geneli hakkında doğru çıkarımda bulunmaya başladığında sonlandırıyor olmamız. Bütün veri için doğru çıktı vermesini beklersek ceza fonksiyonu minimum olacaktır fakat bu sefer elimizde herhangi bir istatiksel dağılımı öğrenmemiş sadece veriyi ezberlemiş bir model olacaktır ki bu da pratikte kullanışsızdır[8].

## Derin Öğrenmenin Gücü Nerede Yatıyor?

Normal yöntemlerin aksine derin öğrenmede imajın hangi bölgelerine nasıl dikkat edileceği yönünde modeli yönlendirmiyoruz. Araştırmacılar ses tanıma, çeviri gibi problemleri çözecek algoritmaların genel olasılıkları kapsamasının mümkün olmadığını düşünüyor. Yani klasik algoritmaların varyasyonlara gerekli tepkiyi veremediklerini düşünüyorlar. Örneğin imajdan yüz tanıma probleminde aynı kişinin saçlarının, sakallarının ve yüz ifadesinin değişmesi gayet normal. Fakat aynı kişinin her fotoğrafta aynı kişi olduğuna karar verecek çok başarılı bir klasik algoritma henüz elimizde yok hatta böyle başarılı bir algoritmanın bulunmasının mümkün olmadığı da iddia ediliyor. Bu noktada yapay sinir ağları genel yaklaşımı değiştirerek bir anlamda algoritmik bakış açısından fonksiyonel bakış açısına geçiş yapıyor, verinin anlamıyla uğraşmaktan ziyade verinin içinde sayısal bir örüntü arıyor. 

Öte yandan bu yöntemde özel bir yönlendirme gerekmediği için çok fazla veriye ve hesaplama gücüne ihtiyaç duyuluyor. Özellikle son yıllarda her yerde duyduğumuz verinin önemine dair konuşmaların bir sebebi de bu. Bahsedilen koşullar sağlandığında derin öğrenme pek çok ses, dil, imaj gibi problemde onlarca yıldır üstüne çalışılan klasik algoritmalardan çok daha iyi çalışıyor. Programcıya düşen temel görev farklı problem tiplerine göre farklı modeller seçmek. Tartışmanın büyük bir kısmı da burada başlıyor. Çünkü bu seçimlerin önemli miktarı sadece deneysel çalışmaların sonuçlarına ve insanların sezgilerine dayalı. Pek çok yöntemin neden çalıştığına dair bir açıklamamız yok çünkü çok yüksek boyutlu uzayda çalışırken teknolojik ve kognitif sınırlara takılıyoruz. Buna rağmen yapay sinir ağlarını anlamlandırma konusunda da ciddi çalışmalar[9] söz konusudur. 

Durum böyleyken nasıl çalıştığını bilmediğimiz ama elimizdeki veri setinde iyi performans gösteren bir programa sürücüsüz arabayı emanet edip edemeyeceğimiz sorusu geliyor akıllara. Fakat her teknolojik gelişmede olduğu gibi uygulamanın altında yatan teori hakkında şüpheler ve endişeler olması gayet normal. Daha önce insanlık tarafından üstesinden gelinen her problem gibi bu problem de kendisi için hayatından fedakarlık edecek pek çok parlak zihni bekliyor. 




* * *

## Kaynakça


1. McCulloch WS, Pitts W. A logical calculus of the ideas immanent in nervous activity. The bulletin of mathematical biophysics, 1943; 5(4) 
2. Farley BG, Clark WA. Simulation of self-organizing systems by digital computer. Transactions of the IRE Professional Group on Information Theory, 1954; 4(4). 
3. Minsky M, Papert S. Perceptrons: An Introduction to Computational Geometry. Cambridge, MA, USA: 1969; MIT Press. 
4. London M, Häusser M. Dendritic computation. Annu. Rev. Neurosci. 2005;28. 
5. Brunel N, Hakim V, Richardson MJ. Single neuron dynamics and computation. Current opinion in neurobiology, 2014; 25. 
6. LeCun Y. The MNIST database of handwritten digits. 1998; http://yann.lecun.com/exdb/mnist/. 
7. Rumelhart DE, Hinton GE, Williams RJ. Learning representations by back-propagating errors. nature, 1986; 323(6088), 533. 
8. Caruana R, Lawrence S, Giles CL. Overfitting in neural nets: Backpropagation, conjugate gradient, and early stopping. In Advances in neural information processing systems 2001; (pp. 402-408). 
9.  Montavon G, Samek W, Müller KR. Methods

