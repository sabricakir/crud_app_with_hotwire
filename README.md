# CRUD APP WITH TURBO STREAMS & TURBO FRAMES
Herkese merhabalar, bu projemde CRUD(Create Read Update Delete) islemlerini gerceklestiren basit bir mesajlasma uygulamasi gelistirdim. Ayni zamanda Turbo frames&streams teknolojileri ile birlikte SPA(Single Page Application) olusturmaya da calistim.

Isterseniz hic uzatmadan projemi tanitma kismina geceyim..

## CREATE
Oncelikle projemde create islemi cok basit bir sekilde isliyor body kismina mesajinizi yaziyorsunuz ve create dediginiz anda sayfa yenilenmeden mesaj ekrana dusuyor. Burda eklemeliyim ki model kisminda body icin validation ekledigimden dolayi body kismi bos kalamiyor eger bos bir sekilde create ederseniz hata mesaji da yine sayfa yenilenmeden ekrana gonderiliyor.

![create 1](https://user-images.githubusercontent.com/84380549/158983886-6d0a2085-e4ca-434c-bbaa-5eb89c8d31e8.png)
![create 2](https://user-images.githubusercontent.com/84380549/158983918-2943e4e1-5d0d-471f-873d-874ea443f706.png)
![create code](https://user-images.githubusercontent.com/84380549/158983924-3e7b1eaf-9422-4e7c-be8d-3c2b7bc05592.png)

## UPDATE
Update isleminde ise create de oldugu gibi edit this message butonuna bastiginiz anda sayfa refresh edilmeden edit formu karsimiza cikiyor ve update message dedigimizde de yine sayfa refresh edilmeden update edilmis mesaj ekranimiza geliyor.

![update 1](https://user-images.githubusercontent.com/84380549/158984023-201365b0-8ed7-425d-aa17-98c50b8ed388.png)
![update 2](https://user-images.githubusercontent.com/84380549/158984027-03effd8d-d337-408c-986d-d59efc74653b.png)
![update code](https://user-images.githubusercontent.com/84380549/158984030-06806833-e8d9-497e-aca4-2b7260e9cda2.png)

## DELETE
Gelelim delete islemine aslinda yine create ve update de oldugu gibi aynı process calisiyor destroy message butonuna bastiginiz anda mesaj db'den siliniyor ve sayfa refresh edilmeden messages listemize bu degisiklik yansiyor.

![delete 1](https://user-images.githubusercontent.com/84380549/158984097-a7742cf4-2ddf-4030-80a4-cd503751fdf9.png)
![delete 2](https://user-images.githubusercontent.com/84380549/158984100-9aa77aea-0d03-4d7a-83aa-e6e7c2482532.png)
![delete code](https://user-images.githubusercontent.com/84380549/158984102-fdf9658a-cb75-4ea3-a199-d1400273449b.png)

## Prepend Message
Create message butonuna bastiginizda dikkatinizi cekecegini umdugum sekilde mesaj en uste ekleniyor. Bunu turbo stream'in **prepend** fonksiyonu ile gerceklestiriyoruz eger mesajlarin alt alta eklenmesini isterseniz prepend yerine **append** demeniz yeterli olacaktır.

## Message Counter & Time Zone & Notifications
Dikkat ettiyseniz sayfanin en ustunde zamani gosteren bir alan var bunu ekleme sebebim siz her mesaji create, update ya da delete ettiginizde sayfanin refresh olmadigini kanitlamak icin eger sayfayi refresh ederseniz goreceksiniz ki zaman degisiyor.
Yine sayfanin basligi olarak en ustte There are **number** messages ibaresini gorecegeniz gibi bunu da stream kullanarak gerceklestirdim ve bu sekilde mesaj eklendiginde ya da silindiginde message counter guncelleniyor.
Son olarak mesaj create update delete ettiginizde yaptiginiz isleme gore yukarida bir notification beliriyor bu notification'in icerigi **message id** created/updated/deleted seklinde ve yine bunu da stream ler araciligiyla gerceklestiriyoruz.

![time code](https://user-images.githubusercontent.com/84380549/158984242-104ccc54-d689-4d0d-a202-69f2ab7a3586.png)
![index code](https://user-images.githubusercontent.com/84380549/158984246-795a1e3c-3092-4db3-bcaa-fd797c4c9e42.png)

