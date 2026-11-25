<div align="center">

# 📚 BilgiKutusu Plus
### İnternet olmasa da bilgi yanında.
**Raspberry Pi 4 için taşınabilir, sıfır bağımlılıklı ve çevrimdışı yerel ağ bilgi deposu.**

<p>
  <img src="https://shields.io" alt="Sürüm 1.0.0" />
  <img src="https://shields.io" alt="Raspberry Pi 4" />
  <img src="https://shields.io" alt="Python 3.9+" />
  <img src="https://shields.io" alt="Çevrimdışı Kullanım" />
</p>

<p>
  <b>🇹🇷 Türkçe</b> · <a href="README.en.md">🇺🇸 English</a>
</p>

<p>
  <a href="#-özellikler">Özellikler</a> •
  <a href="#-pakette-ne-var">Paket İçeriği</a> •
  <a href="#-hızlı-başlangıç">Hızlı Başlangıç</a> •
  <a href="#-raspberry-pide-kurulum">Kurulum</a> •
  <a href="#-ssd-üzerindeki-içeriği-kullanma">SSD Ayarları</a> •
  <a href="#%EF%B8%8F-lisans">Lisans</a>
</p>

<sub>Geliştirici: <a href="https://github.com">@alicanyilmz</a> · Organizasyon: <a href="https://github.com">Bilikon-Project</a></sub>

</div>

---

> [!IMPORTANT]
> **Geliştirme Sürümü · 1.0.0**  
> Bu depo uygulama kodlarını, kurulum betiklerini ve test amaçlı küçük örnek içerikleri barındırır. **Kitap veya büyük medya arşivleri pakete dahil değildir.** Harita ve video dosyaları yalnızca deneme amaçlıdır. Raspberry Pi donanımı üzerinde uzun süreli gerçek yük testleri henüz doğrulanmamıştır.

## 🌿 BilgiKutusu Plus Nedir?

**BilgiKutusu Plus**, telefon, tablet ve bilgisayarlardan aynı yerel ağa (Wi-Fi / LAN) bağlanarak merkezi bir dosya arşivine erişmenizi sağlayan hafif bir web portalıdır. İnternet bağlantısına ihtiyaç duymadan klasörler arasında gezinebilir, anlık dosya araması yapabilir, tarayıcı uyumlu videoları akıcı şekilde izleyebilir ve belgeleri cihazınıza indirebilirsiniz.

* **Sıfır Dış Bağımlılık:** Yalnızca Python standart kütüphanesini kullanır; ek paket kurulumu, veritabanı veya bulut hesabı gerektirmez.
* **Yapay Zekâ İçermez:** Tamamen deterministik, sade ve düşük kaynak tüketimli çalışır.
* **Aile Konumu:** BilgiKutusu ekosisteminin orta segment çözümüdür.

| Paket | Hedef ve Kapsam |
| :--- | :--- |
| **BilgiKutusu Go** | Temel düzey, en hafif başlangıç paketi |
| **BilgiKutusu Plus** *(Bu Depo)* | **Orta seviye; gelişmiş medya akışı, filtreleme ve örnek şablonlar** |
| **BilgiKutusu Pro** | Geniş kapsamlı tam donanımlı kütüphane arayüzü |

---

## ✨ Özellikler

| Özellik | Açıklama |
| :--- | :--- |
| 📂 **Dosya Gezgini** | İçerik klasörlerini sade ve mobil uyumlu web arayüzünden listeler. |
| 🔎 **Anlık Arama & Filtre** | Açık klasör içinde dosya adına ve medya türüne göre hızlı filtreleme yapar. |
| 🎬 **Akıcı Medya Erişimi** | Tarayıcı destekli ses/video dosyalarını ileri-geri sarmayı destekleyen **HTTP Range** istekleriyle oynatır. |
| ⬇️ **Tek Tıkla İndirme** | Seçilen dosyaları doğrudan istemci cihaza (telefon/bilgisayar) kaydeder. |
| 💾 **Harici SSD Desteği** | İçerik dizini yapılandırma dosyasından harici bir diske kolayca yönlendirilebilir. |
| ⚙️ **Arka Plan Hizmeti** | `systemd` kullanan Linux dağıtımlarında sistem açılışında otomatik başlar. |
| 🧭 **%100 Yerel Çalışma** | Dış CDN, font veya API çağrısı yapmaz; tamamen kapalı ağlarda sorunsuz çalışır. |

---

## 📦 Pakette Ne Var?

<details open>
<summary><b>Varsayılan Klasör ve Örnek İçerik Listesini Görüntüle</b></summary>
<br>

| Bölüm | Dahil Olan İçerik | Açıklama |
| :--- | :--- | :--- |
| 🗺️ **Haritalar** | Türkiye şehir konumları görseli | 9 şehir merkezinin yaklaşık koordinatlarını gösteren **örnek harita** (detaylı harita değildir). |
| 🎥 **Eğitim Videoları** | Haritada yönler | Yön, enlem ve boylam okumayı anlatan **24 saniyelik yazılı örnek video**. |
| 🌾 **Tarım** | Ekim takibi CSV çizelgesi | İndirip kendi cihazınızda düzenleyebileceğiniz hazır tablo şablonu. |
| 🎣 **Balıkçılık** | Gözlem defteri CSV çizelgesi | İndirip kendi cihazınızda düzenleyebileceğiniz hazır kayıt şablonu. |
| 📄 **Belgeler** | Başlangıç metni | Temel kullanım yönergelerini içeren kısa doküman. |
| 📚 **Kitaplar** | *Boş içerik alanı* | Kendi e-kitap/PDF arşivinizi eklemeniz için ayrılmış dizin. |
| 🖼️ **Görseller** | *Boş içerik alanı* | Kendi fotoğraf ve görselleriniz için ayrılmış dizin. |

</details>

> [!NOTE]
> Wikipedia/ZIM arşivleri, Kiwix, film/dizi arşivleri ve kapsamlı eğitim kütüphaneleri bu pakete **dahil değildir**. Uygulama internetten otomatik içerik indirmez; yalnızca paylaşma hakkına sahip olduğunuz kendi dosyalarınızı sunucuya eklersiniz.

---

## 🧰 Gereksinimler

* **Donanım:** Raspberry Pi 4 Model B *(4 GB RAM önerilir)*
* **İşletim Sistemi:** Raspberry Pi OS veya Debian tabanlı Linux dağıtımları
* **Yazılım:** Python `3.9` veya üzeri + `systemd`
* **Depolama:** Arşiv boyutunuza uygun SD kart veya harici SSD *(sabit 1 TB zorunluluğu yoktur)*
* **Ağ:** Raspberry Pi ve istemci cihazların bağlı olduğu ortak yerel ağ

> [!TIP]
> **Wi-Fi / Erişim Noktası Notu:** Kurulum betiği cihazı bir Wi-Fi Hotspot'a dönüştürmez. Mevcut yerel ağınızı veya önceden yapılandırılmış BilgiKutusu ağını kullanır; mevcut `nginx`, `Kiwix` ve disk bağlama ayarlarınıza dokunmaz.

---

## 🚀 Hızlı Başlangıç

Kurulum yapmadan uygulamayı yerel ortamda test etmek için depoyu indirin ve proje dizininde terminali açın:

```bash
# Yerel deneme sunucusunu başlatın
bash baslat.sh
```

Tarayıcınızdan **`http://127.0.0.1:8091`** adresine gidin. Sunucuyu kapatmak için terminalde `Ctrl + C` tuşlarına basın.  
*(Not: Hızlı başlangıç modu güvenlik gereği varsayılan olarak yalnızca cihazın kendisinden erişime açıktır.)*

---

## 🔧 Raspberry Pi'de Kurulum

Uygulamayı sistem hizmeti olarak kalıcı kurmak için proje klasöründe şu komutu çalıştırın:

```bash
sudo bash kur.sh
```

**Kurulumun yerleştirdiği dizinler:**
* **Uygulama dosyaları:** `/opt/bilgikutusu-plus`
* **Paylaşılan içerikler:** `/srv/bilgikutusu-plus/icerik`
* **Yapılandırma dosyası:** `/etc/bilgikutusu-plus/config.json`

### 📱 Yerel Ağdan Bağlanma
1. Telefon veya bilgisayarınızı Raspberry Pi ile **aynı Wi-Fi / yerel ağa** bağlayın.
2. Raspberry Pi terminalinde `hostname -I` komutunu çalıştırarak yerel IP adresini öğrenin.
3. İstemci cihazın tarayıcısında **`http://PI_IP_ADRESI:8091`** adresini açın.

> [!WARNING]
> Kurulum betiği, sistemde mevcut bir `BilgiKutusu Plus` kurulumu veya `8091` portunu kullanan başka bir servis tespit ederse işlemi güvenli şekilde durdurur. Betik bir güncelleme aracı değildir; mevcut kurulumunuz varsa önce içerik ve ayarlarınızı yedekleyin.

---

## 💾 SSD Üzerindeki İçeriği Kullanma

Arşivinizi harici bir SSD üzerinden sunmak için `/etc/bilgikutusu-plus/config.json` dosyasındaki `content_dir` değerini SSD'nizin bağlandığı klasör yoluyla güncelleyin:

```json
{
  "content_dir": "/mnt/BilgiKutusu"
}
```

* Arayüz kısayolları `Haritalar`, `EgitimVideolari`, `Tarim` ve `Balikcilik` klasör adlarını tanır. Örnekleri SSD'de de görmek isterseniz ilgili dosyaları bu klasörlere kopyalayabilirsiniz.
* Hizmet kullanıcısının SSD üzerindeki klasörlere **okuma ve erişim (read/execute)** izni olduğundan emin olun.
* Ayarların geçerli olması için hizmeti yeniden başlatın:

```bash
sudo systemctl restart bilgikutusu-plus
```

> [!CAUTION]
> **Güvenlik ve Gizlilik:** Seçilen dizindeki tüm erişilebilir dosyalar yerel ağdaki herkese açık hale gelir. Sistemde kullanıcı girişi/parola koruması yoktur; yalnızca **güvenilen yerel ağlarda** kullanın. Kişisel veya hassas verilerinizi paylaşım klasörüne koymayın ve `8091` portunu internete açmayın. Web arayüzü salt okunurdur (dosya yükleme, silme veya düzenleme yapmaz).

---

## ✅ Durum Kontrolü ve Testler

Hizmetin çalışma durumunu denetlemek ve uygulama testlerini koşmak için:

```bash
# Servis durumunu görüntüle
bash durum.sh

# Otomatik birim testlerini çalıştır
python3 -B -m unittest discover -v
```

Test paketi; dosya erişimi, indirme akışı, HTTP medya aralıkları, Türkçe karakterli dosya adları, yapılandırma doğrulaması, gizli dosyaların engellenmesi ve dizin dışına çıkma (*path traversal*) korumalarını doğrular. Ayrıntılar için [Test Notları](Test-Notlari.md) belgesine göz atabilirsiniz.

---

## 🤝 Katkıda Bulunma

Hata bildirimleri ve özellik önerileri için deponun **Issues** sekmesini kullanabilir, kod iyileştirmeleri için **Pull Request** gönderebilirsiniz. 

* İçerik katkılarında kaynağını ve telif/paylaşım lisansını mutlaka belirtin.
* Gönderimlere kişisel bilgi, parola veya API anahtarı eklemeyin.

Geliştirici Ekip: [Bilikon-Project](https://github.com)

---

## ⚖️ Lisans

Bu yazılım **Ücretsiz ve Ticari Olmayan Kullanım Lisansı 1.0** kapsamında sunulmaktadır. Kaynak kodu incelenebilir; kullanım ve yeniden dağıtım koşulları [LICENSE](LICENSE) dosyasında yer alır. Ticari kullanım yazılı izin gerektirir *(bu lisans OSI tanımına uygun bir açık kaynak lisansı değildir)*.

Temel alınan **BilgiKutusu Go** arşivinin özgün lisans bildirimi [Go-Kaynak-Lisansi.txt](Go-Kaynak-Lisansi.txt) dosyasında korunmaktadır. Üçüncü taraf medya ve şablon içerikleri kendi lisanslarına tabidir.

---

<div align="center">

**BilgiKutusu Plus · Bilgiye Çevrimdışı Erişim**  
[🇹🇷 Türkçe](README.md) · [🇺🇸 English](README.en.md) · [Bilikon-Project](https://github.com)

</div>
