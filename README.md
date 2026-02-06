# ☁️ Fileo - Kişisel Bulut Depo

**Fileo**, Supabase altyapısını kullanan, tamamen sunucusuz (serverless), modern ve güvenli bir dosya depolama ve paylaşım sistemidir. Kullanıcı dostu arayüzü ile dosyalarınızı yükleyebilir, yönetebilir ve **zaman ayarlı** özel linklerle paylaşabilirsiniz.

## 🌟 Özellikler

* **🔒 Güvenli Giriş:** Sadece yetkili kullanıcıların erişebileceği şifreli giriş sistemi.
* **⏳ Süreli Paylaşım:** Dosyalarınız için 1 gün, 1 hafta, 1 ay veya **özel tarihli** geçici indirme linkleri oluşturun.
* **📂 Sürükle & Bırak:** Modern, geniş ve hızlı dosya yükleme alanı.
* **📊 Kota Takibi:** Depolama alanınızın ne kadarını kullandığınızı anlık görsel çubuk ile takip edin.
* **⚡ Gerçek Zamanlı İlerleme:** Dosya yüklerken % yüzdelik ilerleme çubuğu (Progress Bar).
* **📱 Mobil Uyumlu:** Telefon, tablet ve masaüstünde kusursuz çalışan "Responsive" tasarım.
* **🌙 Koyu Mod (Dark Mode):** Göz yormayan, "Flat" ve modern arayüz tasarımı.

---

## ⚠️ ÖNEMLİ: Giriş Mantığı ve Kullanıcı Oluşturma

Bu proje, kullanım kolaylığı sağlamak amacıyla arka planda bazı otomatik dönüştürmeler yapar. Supabase panelinde kullanıcı oluştururken **aşağıdaki kurallara uymanız şarttır**, aksi takdirde giriş yapamazsınız.

### 1. E-Posta Formatı
Giriş ekranında sadece `kullanıcı adı` istenir (Örn: `kerim`). Kod, arka planda bunu otomatik olarak bir e-posta adresine çevirir.
* **Sizin Yazdığınız:** `kerim`
* **Kodun Çevirdiği:** `kerim@kerim.com`

> **Kural:** Supabase panelinde kullanıcı oluştururken e-posta adresini **`kullaniciadi@kullaniciadi.com`** formatında kaydetmelisiniz.

### 2. Büyük/Küçük Harf Duyarlılığı
Kullanıcı deneyimini iyileştirmek için giriş kutusuna yazılan **Kullanıcı Adı** ve **Şifre** otomatik olarak **küçük harfe** çevrilir.
* **Sizin Yazdığınız:** `Kerim` veya `KERIM` -> **Algılanan:** `kerim`
* **Sizin Yazdığınız:** `Sifre123` -> **Algılanan:** `sifre123`

> **Kural:** Supabase panelinde kullanıcı oluştururken şifrenizi **tamamen küçük harflerle** belirleyin.

---

## 🚀 Kendi Sunucunuzda Nasıl Çalıştırırsınız?

Bu projeyi kendi Supabase hesabınızla kullanmak için `index.html` dosyasında sadece 3 satırı değiştirmeniz yeterlidir.

### 1. Supabase Kurulumu
1.  [Supabase](https://supabase.com/) üzerinde yeni bir proje oluşturun.
2.  **Storage** bölümünden `dosyalar` adında yeni bir *Private Bucket* oluşturun.
3.  **Authentication** bölümünden yukarıdaki kurallara uygun (örn: `admin@admin.com`) bir kullanıcı ekleyin.
4.  **Storage Policies** kısmından `dosyalar` bucket'ı için `SELECT`, `INSERT`, `DELETE` izinlerini `authenticated` (giriş yapmış) kullanıcılar için açın.

### 2. Kod Düzenlemesi
`index.html` dosyasını bir metin editörüyle açın ve `// --- SUPABASE AYARLARI ---` bölümünü bulun (yaklaşık 380. satır).

Aşağıdaki alanları kendi proje bilgilerinizle değiştirin:

```javascript
// index.html içindeki bu kısmı bulun ve düzenleyin:

const SB_URL = "BURAYA_SIZIN_SUPABASE_URL_ADRESINIZ_GELECEK";
const SB_KEY = "BURAYA_SIZIN_ANON_PUBLIC_KEY_GELECEK";
const MAX_MB = 500; // İsterseniz kota sınırını buradan (MB cinsinden) değiştirebilirsiniz.
```

* **SB_URL:** Supabase panelinde `Settings > API > Project URL` kısmında bulunur.
* **SB_KEY:** Supabase panelinde `Settings > API > Project API Keys (anon public)` kısmında bulunur.

### 3. Çalıştırın
Dosyayı kaydettikten sonra `index.html` dosyasını tarayıcıda açmanız yeterlidir. GitHub Pages, Netlify veya Vercel üzerinde ücretsiz barındırabilirsiniz.

---

## 🛠️ Kullanılan Teknolojiler

* **Frontend:** HTML5, CSS3, Vanilla JavaScript
* **Backend:** Supabase (Auth & Storage)
* **İkonlar:** Font Awesome 6
* **Font:** Inter (Google Fonts)

## 📜 Lisans

Bu proje [MIT](LICENSE) lisansı ile lisanslanmıştır.
