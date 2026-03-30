# YouTube Video İçerik Üretici

Bu proje bir YouTube içerik üreticisi aracı. Tek bir `index.html` dosyası olarak kur — tüm CSS ve JS inline olacak. Harici kütüphane veya framework KULLANMA.

## Genel Bakış

Kullanıcı video konusu, hedef kitle, video uzunluğu ve içerik tipi girer. Sistem şunları üretir:
- 5 başlık önerisi
- SEO uyumlu açıklama (zaman damgalı)
- 30 etiket
- Thumbnail metin fikirleri
- Senaryo taslağı
- **Fal AI ile oluşturulmuş thumbnail görseli**

Her çıktı ayrı tab'da gösterilir. Her yerde kopyalama butonları var.

## Tasarım

- **Tema:** Koyu (#0a0a0a arka plan)
- **Font:** DM Sans (Google Fonts'tan yükle)
- **Accent:** YouTube kırmızı (#ff0000)
- **Secondary accent:** #cc0000
- **Kartlar:** #141414 arka plan, 1px solid rgba(255,255,255,0.08) border
- **Border radius:** 12px
- **Butonlar:** #ff0000 bg, hover'da #cc0000, border-radius 8px
- **Kopyalama butonu:** Küçük, sağ üst köşe, tıklanınca "Kopyalandı!" feedback
- **Animasyonlar:** Fade-in sonuçlar, tab geçişleri, buton hover efektleri
- **Responsive:** Mobilde tek kolon layout

## Sayfa Yapısı

### Header
- "🎬 Video İçerik Üretici" başlık (h1)
- Alt başlık: "YouTube videolarınız için başlık, açıklama, etiket ve thumbnail oluşturun"
- Sağ üstte YouTube ikonu (SVG inline)

### Form Alanı
4 input, yatay grid (mobilde dikey):

1. **Video Konusu** (text input, placeholder: "Örn: Python ile web scraping öğreniyoruz")
2. **Hedef Kitle** (select dropdown):
   - Başlangıç Seviye
   - Orta Seviye
   - İleri Seviye
   - Genel İzleyici
   - İş Dünyası
   - Öğrenciler
3. **Video Uzunluğu** (select dropdown):
   - Kısa (5-10 dk)
   - Orta (10-20 dk)
   - Uzun (20-40 dk)
   - Çok Uzun (40+ dk)
4. **İçerik Tipi** (select dropdown):
   - Eğitim / Tutorial
   - İnceleme / Review
   - Vlog / Günlük
   - Liste / Top 10
   - Haber / Gündem

**"İçerik Oluştur" butonu** — büyük, kırmızı, tam genişlik altında

### Sonuç Alanı — Tab Navigasyonu

5 tab butonu yatay sıralı:
1. 📝 Başlıklar
2. 📄 Açıklama
3. 🏷️ Etiketler
4. 🖼️ Thumbnail
5. 📋 Senaryo

Her tab'ın içeriği:

#### Tab 1: Başlıklar
- 5 başlık kartı, her biri farklı stil:
  1. Merak uyandıran (soru formatı)
  2. Nasıl yapılır formatı
  3. Liste formatı (rakamla başlayan)
  4. Güçlü ifade (ünlem, büyük iddia)
  5. SEO odaklı (anahtar kelime önde)
- Her kartın sağ üstünde kopyala butonu
- Karakter sayısı göstergesi (60 karakter ideal, renk ile göster: yeşil <60, sarı 60-70, kırmızı >70)

#### Tab 2: Açıklama
- Oluşturulan açıklama tek bir metin bloğunda
- Format:
  ```
  [İlk 2 satır — hook, video özeti]

  🕐 Zaman Damgaları:
  00:00 - Giriş
  [konu bazlı 5-8 zaman damgası]

  📌 Bu Videoda:
  [3-4 madde]

  🔗 Faydalı Linkler:
  [3 placeholder link]

  #etiket1 #etiket2 #etiket3 ... (ilk 5 etiket)

  ---
  [Kanal tanıtım paragrafı]
  ```
- Sağ üstte "Tümünü Kopyala" butonu

#### Tab 3: Etiketler
- 30 etiket, her biri ayrı chip/badge olarak gösterilir
- Chip: #1a1a1a bg, border, hover efekti
- Etiketler 3 gruba ayrılır (her grup 10 etiket):
  - Birincil (konuyla doğrudan ilgili)
  - İkincil (geniş kapsam)
  - Uzun kuyruk (long-tail, spesifik)
- Her grubun başlığı var
- "Tüm Etiketleri Kopyala" butonu (virgülle ayrılmış)
- Toplam karakter sayısı (YouTube 500 karakter limiti göstergesi)

#### Tab 4: Thumbnail
- Üst kısım: 4 thumbnail metin önerisi (kısa, punchy, 3-5 kelime)
- Her öneride: metin, önerilen font boyutu, renk önerisi
- **AI Thumbnail bölümü:**
  - "🎨 AI ile Thumbnail Oluştur" butonu (accent renk, büyük)
  - Butona tıklanınca Fal AI'a istek atılır
  - Loading durumu: pulse animasyonlu placeholder + "Thumbnail oluşturuluyor..." yazısı
  - Sonuç: 1280x720 görsel, altında metin overlay önerileri
  - Görseli indirme linki
- **API Entegrasyonu:**
  ```javascript
  const FAL_KEY = '3c2e1b25-c850-4e3f-9822-9f88b6807a63:e41f4d159c6dd129bb795b812e27d75a';

  async function generateThumbnail(topic) {
    const response = await fetch('https://fal.run/fal-ai/nano-banana-2', {
      method: 'POST',
      headers: {
        'Authorization': `Key ${FAL_KEY}`,
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        prompt: `youtube thumbnail background, ${topic}, dramatic lighting, bold colors, cinematic, 16:9 aspect ratio, high quality, vibrant, professional`,
        negative_prompt: 'text, words, letters, watermark, blurry, low quality',
        image_size: 'landscape_16_9',
        num_inference_steps: 25
      })
    });
    const data = await response.json();
    // data.images[0].url içinde görsel URL
    return data.images[0].url;
  }
  ```
- Hata durumu: "API anahtarı geçerli değil veya bağlantı hatası" mesajı, zarif hata kartı
- Oluşturulan görselin üzerine seçilen metin önerisini overlay olarak gösteren preview

#### Tab 5: Senaryo
- Video uzunluğuna göre bölüm sayısı ayarlanır:
  - Kısa: 4 bölüm
  - Orta: 6 bölüm
  - Uzun: 8 bölüm
  - Çok Uzun: 10 bölüm
- Her bölüm bir kart:
  - Bölüm numarası ve başlığı
  - Süre önerisi
  - Konuşma noktaları (3-4 madde)
  - Görsel/ekran önerisi
- "Tüm Senaryoyu Kopyala" butonu

## İçerik Üretim Mantığı (Template-Based)

5 farklı içerik tipi için ayrı template seti. Her template'te değişkenler kullanıcı girişinden doldurulur. Randomizasyon ile aynı girişte farklı sonuçlar üretilir.

### Başlık Şablonları (her tipten 3 varyant, rastgele seçilir)

```javascript
const titleTemplates = {
  'egitim': {
    curiosity: [
      '{topic} — Bunu Bilmeden Başlama!',
      '{topic} Hakkında Kimsenin Söylemediği Gerçekler',
      '{topic}: Herkesin Yanlış Yaptığı {n} Şey'
    ],
    howto: [
      '{topic} Nasıl Yapılır? (Adım Adım Rehber)',
      'Sıfırdan {topic} Öğren — {audience} İçin',
      '{topic}: Başlangıçtan İleri Seviyeye'
    ],
    // ... diğer formatlar
  },
  // ... diğer tipler
};
```

Değişkenler: `{topic}`, `{audience}`, `{n}` (rastgele 3-10 arası), `{year}` (2026)

### Etiket Üretimi
- Konuyu kelimelere böl
- Her kelime ve kelime kombinasyonları
- "türkçe", "nasıl yapılır", "rehber", "{year}", "{audience} için" gibi ek etiketler
- İçerik tipine göre ek etiketler ("tutorial", "eğitim", "inceleme" vb.)

### Açıklama Üretimi
- İçerik tipine göre hook cümlesi
- Zaman damgaları: bölüm sayısına göre otomatik (video uzunluğunu dakikaya çevir, eşit böl)
- Kanal tanıtım paragrafı sabit template

### Senaryo Üretimi
- Her bölüm: başlık, süre, 3-4 konuşma noktası
- İlk bölüm her zaman "Giriş & Hook"
- Son bölüm her zaman "Kapanış & CTA"
- Ara bölümler içerik tipine göre şablondan

## Veri Yapıları

```javascript
// Kullanıcı girişi
const formData = {
  topic: '',
  audience: '',    // 'baslangic' | 'orta' | 'ileri' | 'genel' | 'is' | 'ogrenci'
  duration: '',    // 'kisa' | 'orta' | 'uzun' | 'cokuzun'
  contentType: ''  // 'egitim' | 'inceleme' | 'vlog' | 'liste' | 'haber'
};

// Üretilen içerik
const generatedContent = {
  titles: [
    { text: '', style: '', charCount: 0 }
  ],
  description: '',
  tags: {
    primary: [],
    secondary: [],
    longTail: []
  },
  thumbnail: {
    textSuggestions: [
      { text: '', fontSize: '', color: '' }
    ],
    aiImageUrl: null
  },
  script: [
    { section: 1, title: '', duration: '', points: [], visual: '' }
  ]
};
```

## Animasyonlar ve UX

- Form submit → sonuç alanı slide-up ile görünür
- Tab geçişlerinde fade efekti (150ms)
- Kopyalama butonunda: ikon değişimi (copy → check), 2sn sonra geri dön
- AI thumbnail oluştururken: skeleton loading, pulse efekti
- Başlık kartlarında hover'da hafif scale(1.02)
- Etiket chip'lerinde hover'da border rengi değişimi
- Sayfa yüklenirken header fade-in

## Responsive Breakpoints

- Desktop (>1024px): 2 kolon form, geniş tab alanı
- Tablet (768-1024px): 2 kolon form, tab içeriği full-width
- Mobil (<768px): tek kolon her şey, tab butonları horizontal scroll

## Önemli Kurallar

- TEK DOSYA: sadece index.html — tüm CSS ve JS inline
- HARİCİ KÜTÜPHANE YOK — saf HTML/CSS/JS
- Google Fonts DM Sans hariç harici kaynak yok
- Tüm metinler Türkçe
- Fal AI entegrasyonu gerçek API çağrısı olacak (API key placeholder ile)
- API key satırı kodda açıkça görünecek: `const FAL_KEY = '3c2e1b25-c850-4e3f-9822-9f88b6807a63:e41f4d159c6dd129bb795b812e27d75a'`
- API hatalarını graceful handle et
- Kopyalama fonksiyonu `navigator.clipboard.writeText` kullanacak
- Performanslı: smooth animasyonlar, 60fps
- Erişilebilir: semantic HTML, ARIA labels
