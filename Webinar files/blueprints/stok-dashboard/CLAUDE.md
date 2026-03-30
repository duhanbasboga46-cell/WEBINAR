# Stok Yonetim Dashboard — Blueprint

## Amac
E-ticaret isletmeleri icin gorsel acidan etkileyici, tam islevli envanter yonetim paneli. Urunleri listeleme, ekleme, duzenleme, silme, arama/filtreleme, SVG grafikler ve CSV export. Tamamiyla localStorage tabanli, API yok.

## Teknik Gereksinimler
- Tek dosya: `index.html` (inline CSS + JS)
- Tema: Koyu (#0a0a0a arka plan), aksent renk #3b82f6 (mavi)
- Font: DM Sans (Google Fonts)
- Dil: Turkce
- Framework yok, sadece vanilla HTML/CSS/JS
- localStorage ile tum veri persistance
- SVG tabanli grafikler (kutuphanesiz, saf SVG)

## API Anahtari
Bu projede API kullanilmiyor. Harici bagimliligi yok.

### .env.example
```
# Bu proje API anahtari gerektirmez
```

## Varsayilan Urun Verileri

Uygulama ilk acilista asagidaki 20 urunle gelmeli (localStorage bossa):

```js
const DEFAULT_PRODUCTS = [
  { id: 1, name: "iPhone 15 Pro Kilif", sku: "KLF-001", category: "Telefon Aksesuari", price: 249.90, cost: 85, stock: 145, minStock: 20, sales7d: 38, status: "active" },
  { id: 2, name: "MacBook Air Cantasi", sku: "CNT-002", category: "Bilgisayar Aksesuari", price: 599.90, cost: 210, stock: 67, minStock: 15, sales7d: 12, status: "active" },
  { id: 3, name: "Bluetooth Kulaklik TWS", sku: "KLK-003", category: "Elektronik", price: 399.90, cost: 150, stock: 8, minStock: 25, sales7d: 31, status: "low_stock" },
  { id: 4, name: "USB-C Hub 7in1", sku: "HUB-004", category: "Bilgisayar Aksesuari", price: 449.90, cost: 180, stock: 52, minStock: 10, sales7d: 9, status: "active" },
  { id: 5, name: "Kablosuz Sarj Standi", sku: "SRJ-005", category: "Telefon Aksesuari", price: 299.90, cost: 95, stock: 0, minStock: 20, sales7d: 0, status: "out_of_stock" },
  { id: 6, name: "Mekanik Klavye RGB", sku: "KLV-006", category: "Bilgisayar Aksesuari", price: 899.90, cost: 380, stock: 23, minStock: 10, sales7d: 7, status: "active" },
  { id: 7, name: "Webcam 1080p", sku: "WEB-007", category: "Elektronik", price: 549.90, cost: 220, stock: 34, minStock: 15, sales7d: 5, status: "active" },
  { id: 8, name: "Ergonomik Mouse Pad", sku: "PAD-008", category: "Ofis", price: 129.90, cost: 35, stock: 210, minStock: 30, sales7d: 45, status: "active" },
  { id: 9, name: "Tablet Standı Ayarlanabilir", sku: "STD-009", category: "Telefon Aksesuari", price: 179.90, cost: 60, stock: 78, minStock: 20, sales7d: 14, status: "active" },
  { id: 10, name: "Mini Projektor", sku: "PRJ-010", category: "Elektronik", price: 2499.90, cost: 1200, stock: 5, minStock: 5, sales7d: 2, status: "low_stock" },
  { id: 11, name: "Akilli Saat Kordon", sku: "KRD-011", category: "Telefon Aksesuari", price: 149.90, cost: 40, stock: 320, minStock: 50, sales7d: 67, status: "active" },
  { id: 12, name: "Laptop Sogutucu", sku: "SGT-012", category: "Bilgisayar Aksesuari", price: 349.90, cost: 130, stock: 41, minStock: 15, sales7d: 8, status: "active" },
  { id: 13, name: "HDMI Kablo 2m", sku: "KBL-013", category: "Kablo & Adaptör", price: 79.90, cost: 20, stock: 0, minStock: 40, sales7d: 0, status: "out_of_stock" },
  { id: 14, name: "Powerbank 20000mAh", sku: "PWR-014", category: "Elektronik", price: 699.90, cost: 280, stock: 56, minStock: 20, sales7d: 19, status: "active" },
  { id: 15, name: "Ekran Koruyucu 3lu Paket", sku: "EKR-015", category: "Telefon Aksesuari", price: 99.90, cost: 15, stock: 540, minStock: 100, sales7d: 89, status: "active" },
  { id: 16, name: "Masa Ustu Mikrofon", sku: "MIK-016", category: "Elektronik", price: 799.90, cost: 350, stock: 12, minStock: 10, sales7d: 4, status: "active" },
  { id: 17, name: "Kablo Düzenleyici Set", sku: "DZN-017", category: "Ofis", price: 59.90, cost: 12, stock: 180, minStock: 40, sales7d: 33, status: "active" },
  { id: 18, name: "LED Masa Lambasi", sku: "LMB-018", category: "Ofis", price: 449.90, cost: 160, stock: 29, minStock: 10, sales7d: 6, status: "active" },
  { id: 19, name: "VR Gozluk Aksesuar Seti", sku: "VR-019", category: "Elektronik", price: 349.90, cost: 120, stock: 3, minStock: 10, sales7d: 1, status: "low_stock" },
  { id: 20, name: "Tasinabilir SSD 1TB", sku: "SSD-020", category: "Bilgisayar Aksesuari", price: 1299.90, cost: 650, stock: 18, minStock: 10, sales7d: 6, status: "active" }
];
```

### Kategoriler
```js
const CATEGORIES = [
  "Telefon Aksesuari",
  "Bilgisayar Aksesuari",
  "Elektronik",
  "Ofis",
  "Kablo & Adaptör"
];
```

## Veri Yapisi

### Urun Objesi
```js
{
  id: number,
  name: string,
  sku: string,           // Stok Kodu
  category: string,
  price: number,         // Satis fiyati (TL)
  cost: number,          // Maliyet (TL)
  stock: number,         // Mevcut stok
  minStock: number,      // Minimum stok esigi
  sales7d: number,       // Son 7 gun satis
  status: "active" | "low_stock" | "out_of_stock",
  createdAt: timestamp
}
```

### Hesaplanan Alanlar
```js
profit = price - cost                    // Birim kar
margin = ((price - cost) / price) * 100  // Kar marji %
stockValue = stock * cost                // Stok degeri (maliyet bazli)
stockRevenue = stock * price             // Stok degeri (satis bazli)
daysUntilOut = stock / (sales7d / 7)     // Tahmini tukeniş suresi (gun)
```

## UI Spesifikasyonu

### Genel Layout
```
+--------------------------------------------------+
|  HEADER: "Stok Yonetim" + Arama + [Urun Ekle]   |
+--------------------------------------------------+
|  ISTATISTIK KARTLARI (4 adet, yatay)             |
|  [Toplam Urun] [Stok Degeri] [Dusuk Stok] [Kar] |
+--------------------------------------------------+
|  GRAFIKLER (2 adet, yan yana)                     |
|  [Kategori Dagilimi - Pie] [Haftalik Satis - Bar]|
+--------------------------------------------------+
|  FILTRELER: Kategori | Durum | Siralama           |
+--------------------------------------------------+
|  URUN TABLOSU                                     |
|  Ad | SKU | Kategori | Fiyat | Stok | Satis | ...|
+--------------------------------------------------+
|  [CSV Indir] [Verileri Sifirla]                   |
+--------------------------------------------------+
```

### Istatistik Kartlari (4 adet)
Her kart icerigi:

1. **Toplam Urun**: Urun sayisi, ikon: kutular
2. **Toplam Stok Degeri**: Maliyet bazli toplam, ikon: TL simgesi, format: "₺125.430"
3. **Dusuk Stok Uyarisi**: stock <= minStock olan urun sayisi, ikon: uyari ucgeni, kirmizi ton
4. **Ortalama Kar Marji**: Tum urunlerin ortalama margin'i, ikon: yukari ok, yesil ton

Animasyon: Sayfa yuklendiginde sayilar 0'dan hedef degere sayar (1.5sn, easeOut). `requestAnimationFrame` kullan.

### SVG Grafikler

#### Kategori Dagilimi (Pie/Donut Chart)
- Her kategori icin dilim, renk kodlu
- Ortasinda toplam urun sayisi
- Hover'da dilim buyusun, tooltip gostersin (kategori adi + urun sayisi + yuzde)
- Renkler: her kategoriye sabit renk ata
- Donut seklinde (ic yaricap = dis yaricap * 0.6)

#### Haftalik Satis (Bar Chart)
- X ekseni: urun adlari (top 8 en cok satan)
- Y ekseni: satis adedi
- Bar rengi: aksent mavi, hover'da acik mavi
- Her barin ustunde deger etiketi
- Gridlines yatay

### Filtre Bari
- Kategori dropdown: "Tum Kategoriler" + CATEGORIES listesi
- Durum dropdown: "Tumu", "Aktif", "Dusuk Stok", "Tukendi"
- Siralama dropdown: "Ada Gore (A-Z)", "Fiyata Gore (Artan)", "Fiyata Gore (Azalan)", "Stoka Gore (Azalan)", "Satisa Gore (Azalan)"
- Arama: header'daki arama input'u ile canli filtreleme (ad ve SKU'da ara)

### Urun Tablosu
Sutunlar:
| Sutun | Genislik | Icerik |
|-------|----------|--------|
| Urun Adi | flex | Ad + SKU alt satir |
| Kategori | 140px | Badge seklinde |
| Fiyat | 100px | ₺249,90 formati |
| Maliyet | 100px | ₺85,00 formati |
| Kar Marji | 90px | %65.9 + renk (yesil >40, sari >20, kirmizi <20) |
| Stok | 80px | Sayi + progress bar (stock/minStock*100 bazli) |
| 7g Satis | 80px | Sayi |
| Durum | 100px | Renkli badge: Aktif/Dusuk/Tukendi |
| Islemler | 80px | Duzenle + Sil ikonlari |

Tablo satirlari hover efekti. Tukenmis urunler hafif kirmizi arka plan.

### Urun Ekle/Duzenle Modal
- Karanlik overlay
- Bos form (ekle) veya dolu form (duzenle)
- Alanlar: name, sku, category (select), price, cost, stock, minStock
- Kaydet + Iptal butonlari
- Form validasyonu: tum alanlar zorunlu, fiyat > maliyet kontrolu

### CSV Export
Buton tiklandiginda tum urun verisini CSV olarak indir. Dosya adi: `stok-raporu-YYYY-MM-DD.csv`. Turkce basliklar. UTF-8 BOM ile (Excel uyumlu).

### Verileri Sifirla
Onay modal'i gosterip localStorage'i temizle ve varsayilan veriyle yeniden yukle.

### Responsive
- 1024px alti: grafikler alt alta
- 768px alti: istatistik kartlari 2x2 grid, tablo yatay scroll
- 480px alti: kartlar tek kolon

### Animasyonlar
- Sayfa yuklenme: kartlar staggered fade-in (100ms aralik)
- Sayi animasyonu: 0'dan hedefe 1.5sn (counter animation)
- Tablo satirlari: fade-in
- Modal: scale(0.95) -> scale(1) transition
- Silme: satir kayarak kuculsun ve kaybolsun
- Grafik: pie chart dilimleri saat yonunde animasyonla acilsin
- Bar chart: barlar asagidan yukari buyusun

### Renk Paleti
```css
--bg-primary: #0a0a0a;
--bg-secondary: #111111;
--bg-card: #1a1a1a;
--bg-table-row: #141414;
--bg-table-hover: #1e1e1e;
--border: #2a2a2a;
--text-primary: #f5f5f5;
--text-secondary: #a0a0a0;
--accent: #3b82f6;
--accent-hover: #2563eb;
--success: #22c55e;
--warning: #f59e0b;
--error: #ef4444;
```

## localStorage Yapisi

```js
// Key: 'stok-dashboard-products'
// Value: JSON array of product objects

// Key: 'stok-dashboard-initialized'
// Value: 'true' (ilk yukleme yapildi mi)
```

## Onemli Notlar
- Fiyat formatlama: Turkce locale, ₺ simgesi, 2 ondalik
- SKU otomatik onerisi: Kategori kisaltmasi + 3 haneli artan sayi
- Status otomatik guncelleme: stock === 0 -> out_of_stock, stock <= minStock -> low_stock, diger -> active
- Grafiklerin animasyonlu olmasina onem ver, dashboard hissi versin
- Silme isleminde onay iste
- Tablo bos ise "Urun bulunamadi" mesaji goster
