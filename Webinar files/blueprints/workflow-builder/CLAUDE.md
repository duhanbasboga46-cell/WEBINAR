# Gorsel Workflow Builder

## Genel Bakis
n8n tarzi gorsel bir workflow olusturucu. Kullanici surukle-birak ile node'lar ekler, birbirine baglar ve ornek bir otomasyon akisini canli olarak calistirir. Tamamen frontend — API gerektirmez.

## Teknik Gereksinimler
- **Tek dosya:** `index.html` (inline CSS + JS)
- **Font:** DM Sans (Google Fonts)
- **Tema:** Koyu (#0a0a0a arka plan), aksent renk #ff6d5a (n8n turuncusu)
- **Dil:** Turkce
- **Framework:** Yok — vanilla HTML/CSS/JS

## Sayfa Yapisi

### Layout
Sol tarafta dikey sidebar (node paleti, 240px genislik), sag tarafta tam ekran canvas alani.

### Header (canvas ustunde)
- Sol: Logo/baslik "Workflow Builder"
- Sag: "Calistir" butonu (#ff6d5a), "Temizle" butonu (outline)

### Sol Sidebar — Node Paleti
Baslik: "Nodelar"
Kategorilere ayrilmis, her node bir ikon + isim:

**Tetikleyiciler:**
1. Webhook (ikon: zap) — Gelen HTTP istegi
2. Schedule (ikon: clock) — Zamanlanmis calisma

**Islemler:**
3. HTTP Request (ikon: globe) — API cagrisi
4. Email Gonder (ikon: mail) — Email gonderimi
5. Google Sheets (ikon: table) — Tablo islemleri
6. Slack Mesaj (ikon: message-square) — Bildirim
7. Database (ikon: database) — Veritabani sorgusu
8. Code (ikon: code) — Ozel kod calistir

**Mantik:**
9. IF Kosul (ikon: git-branch) — Kosullu dallanma
10. Filter (ikon: filter) — Veri filtreleme
11. Transform (ikon: shuffle) — Veri donusumu
12. Merge (ikon: git-merge) — Akislari birlestir

Node ikonlari icin inline SVG kullan (basit path'ler). Her node sidebar'da 44px yuksekliginde kart olarak gorunur.

### Canvas Alani
- Acik gri grid arka plan (nokta pattern, #1a1a1a uzerinde #2a2a2a noktalar)
- Node'lar canvas uzerine tikladiginda sidebar'daki secili node tipinden olusturulur
- Her node canvas'ta suruklenebilir (mousedown/mousemove/mouseup)
- Node boyutu: 180px x 80px, rounded (12px), koyu arka plan (#1e1e1e), border (#333)
- Node uzerinde: ikon (sol), isim (orta), ayar butonu (sag ust), silme butonu (sag ust x)

### Node Baglantilari
- Her node'un sag tarafinda cikis noktasi (kucuk daire, 10px), sol tarafinda giris noktasi
- Cikis noktasindan surukleyerek baska node'un giris noktasina bagla
- Baglanti cizgisi: SVG cubic bezier curve, #ff6d5a renk, 2px kalinlik
- Baglanti uzerine hover'da silme ikonu goster

### Node Ayar Paneli
Bir node'a cift tiklandiginda sag taraftan slide-in panel (320px):
- Node ismi (duzenlenebilir input)
- Node tipine ozel ayarlar:
  - Webhook: URL, method (GET/POST)
  - HTTP Request: URL, method, headers (textarea)
  - Email: Alici, konu, govde
  - Filter: Alan adi, operator (esit/icerir/buyuk/kucuk), deger
  - IF Kosul: Kosul ifadesi
  - Schedule: Cron ifadesi veya "Her X dakika" secimi
  - Google Sheets: Tablo ID, sayfa adi, islem (oku/yaz)
  - Slack: Kanal, mesaj
  - Database: Sorgu (textarea)
  - Code: Kod editoru (textarea, monospace font)
  - Transform: Kaynak alan, hedef alan, islem
  - Merge: Mod (birlestir/kesisim)
- "Kaydet" ve "Iptal" butonlari

### On Yuklu Ornek Workflow
Sayfa acildiginda hazir bir workflow yuklu gelsin:
1. **Webhook** (x:100, y:200) — "Yeni Musteri Formu"
2. **Filter** (x:350, y:200) — "Email Dogrula"
3. **Slack Mesaj** (x:600, y:120) — "Takima Bildir"
4. **Google Sheets** (x:600, y:300) — "CRM'e Kaydet"
5. **Email Gonder** (x:850, y:200) — "Hosgeldin Email'i"

Baglantilar: 1→2, 2→3, 2→4, 3→5, 4→5

### Calistir Animasyonu
"Calistir" butonuna basildiginda:
1. Tum node'lar soluk olur (opacity 0.4)
2. Ilk node'dan baslayarak sirayla her node aktif olur:
   - Node border #ff6d5a olur
   - Node etrafinda pulse animasyonu (box-shadow genisleyerek kaybolur)
   - Baglanti cizgisi uzerinde hareket eden nokta animasyonu (dash-offset)
   - Her node 800ms aktif kalir
3. Dallanma varsa paralel animasyon
4. Son node'a ulasildiginda "Basarili!" toast mesaji goster

### Ek Ozellikler
- Canvas zoom: Ctrl+scroll ile %50-%200 arasi
- Mini-map: Sag alt kosede kucuk onizleme (opsiyonel, yoksa sorun degil)
- Undo/Redo: Ctrl+Z / Ctrl+Shift+Z (son 20 islem)
- Node kopyalama: Secili node uzerinde Ctrl+D

## Stil Detaylari

```
Arka plan: #0a0a0a
Canvas: #111111
Node arka plan: #1e1e1e
Node border: #333333
Node aktif border: #ff6d5a
Aksent: #ff6d5a
Yazi: #e5e5e5
Ikincil yazi: #888888
Sidebar: #111111
Panel: #161616
Buton hover: #ff8a75
Grid noktalar: #2a2a2a
```

## Responsive
- Minimum 1024px genislik icin optimize
- Mobilde uyari goster: "Bu uygulama masaustu icin optimize edilmistir"

## Onemli
- Tum state bellekte tutulur (localStorage gerekmez)
- SVG baglantilari canvas koordinatlarina gore dinamik hesaplanir
- Node surukleme sirasinda baglantilar canli guncellenir
- Performans: 50+ node'da kasma olmamali
