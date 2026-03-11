# 📝 Python Terminal Tabanlı To-Do List (Görev Yöneticisi)

## 📌 Proje Hakkında

Bu proje, kullanıcıların günlük görevlerini komut satırı (terminal) üzerinden hızlı ve pratik bir şekilde yönetmelerini sağlayan Python tabanlı bir "Yapılacaklar Listesi" (To-Do List) uygulamasıdır. Kullanıcı dostu bir menü arayüzüne sahip olan program; görev ekleme, listeleme, güncelleme ve silme (CRUD) işlemlerini zaman damgası (tarih ve saat) desteğiyle gerçekleştirir.

## 🚀 Özellikler

* **Zaman Damgalı Kayıt:** Eklenen her göreve otomatik olarak o anın tarih ve saat bilgisi eklenir.
* **Dinamik Güncelleme:** Bir görev düzenlendiğinde, görev metniyle birlikte tarih bilgisi de güncellenir ve "(Güncellendi)" etiketi alır.
* **Hata Yönetimi (Error Handling):** Kullanıcının menüde harf girmesi veya olmayan bir kayıt numarasını seçmesi gibi durumlara karşı korumalıdır. Program çökmez, kullanıcıyı uyarır.
* **Geçici Veri Saklama:** Program çalıştığı sürece veriler liste ve sözlük (dictionary) veri yapıları kullanılarak bellekte (RAM) tutulur.

## 🛠️ Kurulum ve Çalıştırma

Uygulama, Python'un standart kütüphaneleri dışında hiçbir harici modül gerektirmez.

1. Bilgisayarınızda Python 3.x sürümünün yüklü olduğundan emin olun.
2. Proje dosyasını (örn: `todo.py`) bilgisayarınıza indirin.
3. Terminal veya Komut İstemcisi'ni (CMD) açın.
4. Dosyanın bulunduğu dizine gidin ve aşağıdaki komutu çalıştırın:
```bash
python todo.py

```



## 📖 Kullanım Kılavuzu

Program başlatıldığında ekrana 5 seçenekli bir menü gelir. İşlem yapmak için menüdeki numaraları tuşlayıp `Enter`'a basmanız yeterlidir.

* **1. Yeni Kayıt Aç:** Sizden bir görev metni girmeniz istenir. Görevi yazıp onayladığınızda, sistem o anki tarih ve saati alarak görevi listeye ekler.
* **2. Kayıtları Görüntüle:** Oluşturduğunuz tüm görevleri, eklenme/güncellenme tarihleriyle birlikte numaralandırılmış bir liste halinde ekrana yazdırır. Eğer liste boşsa "Kayıt Bulunamadı" uyarısı verir.
* **3. Kayıtları Güncelle/Düzenle:** Mevcut görevleri listeler ve değiştirmek istediğiniz görevin numarasını sorar. Numarayı ve yeni görev metnini girdiğinizde kayıt yenilenir. Tarih bilgisi o anki zamanla değiştirilerek sonuna güncellendiğine dair bir not düşülür.
* **4. Kayıtları Sil:** Sistemdeki görevleri listeler. Silmek istediğiniz görevin numarasını girdiğinizde, o görev listeden kalıcı olarak çıkartılır.
* **5. Çıkış Yap:** Döngüyü sonlandırır ve uygulamayı güvenli bir şekilde kapatır.

## 💻 Teknik Altyapı ve Veri Yapısı (Geliştirici Notları)

* **Dil:** Python 3
* **Kütüphaneler:** `datetime` (Tarih ve saat verilerini formatlamak için kullanıldı).
* **Döngü Mekanizması:** Program, `while True:` döngüsü içerisinde çalışarak kullanıcı **5** numaralı çıkış komutunu verene kadar aktif kalır.
* **Veri Yapısı:** Görevler `baslik = []` isimli bir liste (list) içinde tutulmaktadır. Her bir liste elemanı, `{"gorev": "Görev Metni", "tarih": "Gün.Ay.Yıl Saat:Dakika"}` yapısında bir sözlük (dictionary) objesidir. Bu sayede verilere `indeks` numaraları ve `anahtar` (key) kelimeler üzerinden O(1) karmaşıklığı ile hızlıca erişilir.
* **Güvenlik/Doğrulama:** Kullanıcı girişleri `isdigit()` fonksiyonu ile kontrol edilerek string/integer uyuşmazlığından kaynaklı hataların önüne geçilmiştir.
