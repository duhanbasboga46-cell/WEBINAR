# Blueprint Kullanım Rehberi

Her blueprint bir CLAUDE.md (proje spesifikasyonu) ve kur.md (build komutu) içerir. Claude Code'a `/kur` dediğinde tüm uygulamayı sıfırdan oluşturur.

---

## Genel Kullanım (Her Blueprint İçin Aynı)

```bash
# 1. Yeni klasör oluştur
mkdir proje-adi && cd proje-adi

# 2. Blueprint dosyalarını kopyala
cp /path/to/blueprints/BLUEPRINT-ADI/CLAUDE.md .
mkdir -p .claude/commands
cp /path/to/blueprints/BLUEPRINT-ADI/kur.md .claude/commands/

# 3. Claude Code'u aç
claude

# 4. Kur komutunu çalıştır
/kur
```

Hepsi bu. Claude Code CLAUDE.md'yi okur, tüm uygulamayı tek bir `index.html` olarak oluşturur ve tarayıcıda açar.

---

## E-TİCARET

### 1. Ürün Açıklama & Görsel Yazıcı
**Klasör:** `urun-aciklama-yazici/`
**Ne yapar:** Ürün adı ve özelliklerini giriyorsun, profesyonel açıklama + Fal AI ile gerçek ürün fotoğrafı üretiyor.
**API:** Fal AI (görsel üretimi)

```bash
mkdir urun-yazici && cd urun-yazici
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/urun-aciklama-yazici/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/urun-aciklama-yazici/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Ürün adı yaz → Kategori seç → Özellikler gir → "Oluştur" tıkla → "Görsel Oluştur" ile Fal AI'dan gerçek ürün fotoğrafı al

---

### 2. Stok Yönetim Dashboard
**Klasör:** `stok-dashboard/`
**Ne yapar:** Tam bir envanter yönetim paneli — ürünler, stok takibi, grafikler, CSV export.
**API:** Yok (localStorage)

```bash
mkdir stok && cd stok
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/stok-dashboard/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/stok-dashboard/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** 20 ürün hazır yüklü. Ekle, düzenle, sil, filtrele, CSV'ye aktar.

---

### 3. E-ticaret Fiyat Hesaplayıcı
**Klasör:** `fiyat-hesaplayici/`
**Ne yapar:** Maliyet gir, kar marjı belirle, tüm pazaryerlerinde fiyat karşılaştır. Apify ile Google Shopping'den gerçek rakip fiyatları çeker.
**API:** Apify (Google Shopping scraper)

```bash
mkdir fiyat && cd fiyat
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/fiyat-hesaplayici/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/fiyat-hesaplayici/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Maliyet + kargo + marj gir → otomatik hesaplama → "Rakip Fiyat Ara" ile gerçek Google Shopping verisi çek

---

### 4. QR Dijital Menü Oluşturucu
**Klasör:** `qr-menu/`
**Ne yapar:** Restoran menüsü düzenleyici + canlı önizleme. Fal AI ile yemek görselleri üretiyor.
**API:** Fal AI (yemek fotoğrafı)

```bash
mkdir qr-menu && cd qr-menu
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/qr-menu/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/qr-menu/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** 24 yemek hazır yüklü. Düzenle, ekle, sil → Her yemeğe "Görsel Oluştur" ile AI fotoğraf üret → QR kod oluştur

---

## YOUTUBE

### 5. Video İçerik Üretici
**Klasör:** `video-icerik-uretici/`
**Ne yapar:** Video konusu gir, başlık/açıklama/tag/script üretir. Fal AI ile thumbnail oluşturur.
**API:** Fal AI (thumbnail)

```bash
mkdir youtube-icerik && cd youtube-icerik
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/video-icerik-uretici/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/video-icerik-uretici/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Konu + hedef kitle + süre gir → 5 başlık, açıklama, 30 tag, script taslağı → "Thumbnail Oluştur" ile gerçek görsel

---

### 6. Thumbnail Tasarımcı
**Klasör:** `thumbnail-olusturucu/`
**Ne yapar:** Canvas tabanlı thumbnail editörü. Fal AI ile AI arka plan üretir.
**API:** Fal AI (arka plan)

```bash
mkdir thumbnail && cd thumbnail
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/thumbnail-olusturucu/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/thumbnail-olusturucu/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Şablon seç veya "AI Arka Plan" ile açıklama yaz → Fal AI görsel üretir → Metin ekle, sürükle, boyutlandır → PNG indir

---

### 7. YouTube Analytics Dashboard
**Klasör:** `analytics-dashboard/`
**Ne yapar:** YouTube kanal analitik paneli. Apify ile gerçek kanal verisi çeker.
**API:** Apify (YouTube scraper)

```bash
mkdir yt-analytics && cd yt-analytics
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/analytics-dashboard/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/analytics-dashboard/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Kanal URL'si gir → "Verileri Çek" → gerçek abone/video/izlenme verileri gelir → Grafikler ve tablolar

---

## N8N & OTOMASYON

### 8. Görsel Workflow Builder
**Klasör:** `workflow-builder/`
**Ne yapar:** n8n tarzı görsel otomasyon akışı oluşturucu. Sürükle-bırak node'lar.
**API:** Yok

```bash
mkdir workflow && cd workflow
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/workflow-builder/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/workflow-builder/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Sol panelden node ekle → Canvas'ta sürükle → Bağlantı oluştur → "Çalıştır" ile animasyonlu akış izle

---

### 9. Lead Scraper Panel
**Klasör:** `lead-scraper-panel/`
**Ne yapar:** Google Maps'ten gerçek işletme verisi çeken lead scraping paneli.
**API:** Apify (Google Maps scraper)

```bash
mkdir lead-scraper && cd lead-scraper
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/lead-scraper-panel/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/lead-scraper-panel/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** "Yeni Tarama" → "berber istanbul" yaz → Apify gerçek işletmeleri çeker → Tablo + CSV export

---

### 10. Email Kampanya Yöneticisi
**Klasör:** `email-kampanya-yoneticisi/`
**Ne yapar:** Cold email kampanya yönetim aracı — sekanslar, merge fields, dönüşüm hunisi.
**API:** Yok

```bash
mkdir email-kampanya && cd email-kampanya
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/email-kampanya-yoneticisi/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/email-kampanya-yoneticisi/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** 3 kampanya hazır yüklü. Email sekansı düzenle, merge field'ları gör, dönüşüm oranlarını takip et.

---

## UYGULAMALAR

### 11. Randevu Sistemi
**Klasör:** `randevu-sistemi/`
**Ne yapar:** Haftalık takvim, online randevu alma, müşteri yönetimi.
**API:** Yok

```bash
mkdir randevu && cd randevu
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/randevu-sistemi/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/randevu-sistemi/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Takvimde slot'a tıkla → Müşteri bilgilerini gir → Randevu oluştur. 10+ randevu hazır yüklü.

---

### 12. Fatura Oluşturucu
**Klasör:** `fatura-olusturucu/`
**Ne yapar:** Profesyonel fatura oluşturucu — KDV hesaplama, canlı önizleme, PDF indirme.
**API:** Yok

```bash
mkdir fatura && cd fatura
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/fatura-olusturucu/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/fatura-olusturucu/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Firma + müşteri bilgisi gir → Kalem ekle (fiyat + KDV) → Canlı fatura önizleme → "PDF İndir"

---

### 13. Restoran Sipariş Sistemi
**Klasör:** `restoran-siparis-sistemi/`
**Ne yapar:** 3 ekranlı restoran sistemi — müşteri menü, mutfak ekranı, yönetim paneli. Gerçek zamanlı.
**API:** Yok

```bash
mkdir restoran && cd restoran
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/restoran-siparis-sistemi/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/restoran-siparis-sistemi/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** `#menu` → Sipariş ver. `#mutfak` → Siparişler gerçek zamanlı gelir (ayrı sekmede aç). `#yonetim` → Dashboard.

---

## DİĞER

### 14. Portfolio Site Builder
**Klasör:** `portfolio-site-builder/`
**Ne yapar:** Görsel portfolio oluşturucu. Fal AI ile profil fotoğrafı ve proje görseli üretiyor.
**API:** Fal AI (profil foto + proje görseli)

```bash
mkdir portfolio && cd portfolio
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/portfolio-site-builder/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/portfolio-site-builder/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Bölüm ekle/sırala → "AI Profil Fotoğrafı" ile avatar üret → Tema seç → "Kodu İndir" ile HTML al

---

### 15. AI Chatbot Widget Builder
**Klasör:** `ai-chatbot-widget/`
**Ne yapar:** İşletmeler için chatbot widget oluşturucu. Fal AI ile bot avatarı üretiyor.
**API:** Fal AI (bot avatarı)

```bash
mkdir chatbot && cd chatbot
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/ai-chatbot-widget/CLAUDE.md .
mkdir -p .claude/commands
cp ~/Downloads/CLAUDE_SITE/doa-starter-kit/blueprints/ai-chatbot-widget/kur.md .claude/commands/
claude
# → /kur
```

**Kullanım:** Bot adı + renk ayarla → Soru-cevap çiftleri ekle → "Bot Avatarı Oluştur" → Canlı chat testi yap → "Widget Kodunu Kopyala"

---

## Hızlı Referans

| # | Blueprint | API | Wow Faktörü |
|---|-----------|-----|-------------|
| 1 | Ürün Açıklama Yazıcı | Fal AI | Gerçek ürün fotoğrafı üretiyor |
| 2 | Stok Dashboard | — | Tam çalışan envanter sistemi |
| 3 | Fiyat Hesaplayıcı | Apify | Google Shopping'den gerçek fiyat çekiyor |
| 4 | QR Menü | Fal AI | Yemek fotoğrafları AI ile üretiliyor |
| 5 | Video İçerik Üretici | Fal AI | Thumbnail AI ile üretiliyor |
| 6 | Thumbnail Tasarımcı | Fal AI | AI arka plan üretip canvas'a koyuyor |
| 7 | YouTube Analytics | Apify | Gerçek kanal verisi çekiyor |
| 8 | Workflow Builder | — | n8n tarzı görsel akış oluşturucu |
| 9 | Lead Scraper | Apify | Google Maps'ten gerçek işletme çekiyor |
| 10 | Email Kampanya | — | Cold email funnel yönetimi |
| 11 | Randevu Sistemi | — | Tam takvim + booking sistemi |
| 12 | Fatura Oluşturucu | — | Canlı önizleme + PDF indirme |
| 13 | Restoran Sistemi | — | 3 ekran, gerçek zamanlı sipariş |
| 14 | Portfolio Builder | Fal AI | AI profil foto + proje görseli |
| 15 | Chatbot Widget | Fal AI | AI bot avatarı üretiliyor |
