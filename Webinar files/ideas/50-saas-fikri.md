# 50 B2B SaaS & Uygulama Fikri

Claude Code ile 2-4 haftada tek başına kurulabilecek, gerçekçi ve karlı iş fikirleri. Her fikir Türkiye'deki işletmelerin günlük yaşadığı somut bir problemi çözüyor.

---

## Sağlık & Klinikler

### 1. RandevuPilot
- **Sektör:** Sağlık & Klinikler
- **Problem:** Küçük klinikler hala telefonla randevu alıyor, hastaların %30'u randevuya gelmiyor, hatırlatma sistemi yok.
- **Çözüm:** WhatsApp üzerinden otomatik randevu hatırlatma ve onay sistemi. Hasta "evet" yazarsa onaylanır, "hayır" yazarsa slot otomatik açılır.
- **Hedef müşteri:** Diş klinikleri, güzellik merkezleri, fizik tedavi merkezleri (1-5 doktor)
- **Fiyatlandırma:** $49/ay (tek lokasyon), $99/ay (çoklu lokasyon)
- **Araçlar:** Claude Code, Supabase, n8n, WhatsApp Business API, Stripe

### 2. ReçeteTakip
- **Sektör:** Sağlık & Klinikler
- **Problem:** Eczaneler ve klinikler kronik hasta ilaç takibini manuel yapıyor, ilaç bitim tarihleri kaçırılıyor.
- **Çözüm:** Kronik hastaların ilaç bitiş tarihlerini takip edip otomatik SMS/WhatsApp ile hatırlatma gönderen sistem.
- **Hedef müşteri:** Eczaneler, aile hekimleri
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Supabase, n8n, Twilio

### 3. KlinikPano
- **Sektör:** Sağlık & Klinikler
- **Problem:** Klinik sahipleri günlük hasta sayısı, gelir, doluluk oranı gibi metrikleri Excel'den takip etmeye çalışıyor.
- **Çözüm:** Basit bir dashboard: günlük/haftalık/aylık hasta sayısı, gelir, en çok yapılan işlemler, doktor başına performans.
- **Hedef müşteri:** 2-10 doktorlu özel klinikler
- **Fiyatlandırma:** $79/ay
- **Araçlar:** Claude Code, Supabase, Chart.js, Stripe

### 4. HastaFormu
- **Sektör:** Sağlık & Klinikler
- **Problem:** Hastalar her gelişinde kağıt form dolduruyor, veriler dijitalleştirilemiyor.
- **Çözüm:** Dijital hasta kabul formu — tablet veya telefon üzerinden dolduruluyor, otomatik dosyalanıyor, tekrar gelişte bilgiler hazır.
- **Hedef müşteri:** Diş klinikleri, poliklinikler, medikal estetik merkezleri
- **Fiyatlandırma:** $29/ay
- **Araçlar:** Claude Code, Supabase, React/Next.js

### 5. LabisSonuç
- **Sektör:** Sağlık & Klinikler
- **Problem:** Laboratuvar sonuçları hazır olduğunda hasta arayıp bilgilendirmek zaman kaybı.
- **Çözüm:** Sonuç hazır olduğunda hastaya otomatik bildirim gönderen ve güvenli link ile sonucu paylaşan sistem.
- **Hedef müşteri:** Özel laboratuvarlar, küçük hastaneler
- **Fiyatlandırma:** $59/ay
- **Araçlar:** Claude Code, Supabase, n8n, WhatsApp Business API

---

## Eğitim & Kurslar

### 6. KursKasası
- **Sektör:** Eğitim & Kurslar
- **Problem:** Küçük kurs merkezleri (dil kursu, müzik, sanat) öğrenci kayıt, ödeme takibi ve devamsızlık yönetimini kağıt/Excel ile yapıyor.
- **Çözüm:** Öğrenci kaydı, taksit takibi, devamsızlık bildirimi ve veli iletişimini tek panelden yöneten sistem.
- **Hedef müşteri:** Dil kursları, müzik okulları, sanat atölyeleri (10-100 öğrenci)
- **Fiyatlandırma:** $49/ay (50 öğrenciye kadar), $99/ay (sınırsız)
- **Araçlar:** Claude Code, Supabase, Stripe, n8n

### 7. ÖdevBot
- **Sektör:** Eğitim & Kurslar
- **Problem:** Özel ders öğretmenleri ödev verme, takip etme ve geri bildirim sürecini WhatsApp'tan yönetmeye çalışıyor.
- **Çözüm:** Öğretmenin ödev atadığı, öğrencinin yüklediği, otomatik hatırlatma gönderen ve ilerlemeyi raporlayan basit portal.
- **Hedef müşteri:** Özel ders öğretmenleri, küçük etüt merkezleri
- **Fiyatlandırma:** $29/ay
- **Araçlar:** Claude Code, Supabase, Cloudflare R2 (dosya depolama)

### 8. SınıfHarita
- **Sektör:** Eğitim & Kurslar
- **Problem:** Anaokulu ve kreşler velilere günlük aktivite raporu vermekte zorlanıyor.
- **Çözüm:** Öğretmenin günlük aktiviteleri (yemek, uyku, etkinlik, fotoğraf) hızlıca girdiği ve velilerin anlık görebildiği uygulama.
- **Hedef müşteri:** Anaokulu ve kreşler
- **Fiyatlandırma:** $59/ay (sınıf başına)
- **Araçlar:** Claude Code, Supabase, Cloudflare R2, PWA

### 9. EğitimTakvim
- **Sektör:** Eğitim & Kurslar
- **Problem:** Çok şubeli kurs merkezleri sınıf/salon planlamasını çakışmalar yaşayarak yapıyor.
- **Çözüm:** Drag & drop takvim ile ders programı oluşturma, salon çakışma kontrolü, öğretmen müsaitlik yönetimi.
- **Hedef müşteri:** 2+ şubeli kurs merkezleri, dans okulları, spor akademileri
- **Fiyatlandırma:** $79/ay
- **Araçlar:** Claude Code, Supabase, FullCalendar.js

### 10. MezunBağ
- **Sektör:** Eğitim & Kurslar
- **Problem:** Eğitim kurumları mezunlarla bağ kuramıyor, referans ve upsell fırsatlarını kaçırıyor.
- **Çözüm:** Mezun CRM'i — mezunların kariyer durumu, iletişim bilgileri, otomatik yıldönümü mesajları, yeni kurs önerileri.
- **Hedef müşteri:** Bootcamp'ler, sertifika programları, profesyonel eğitim kurumları
- **Fiyatlandırma:** $49/ay
- **Araçlar:** Claude Code, Supabase, n8n, Resend (email)

### 11. SınavHazır
- **Sektör:** Eğitim & Kurslar
- **Problem:** Dershane ve kurs öğretmenleri test/sınav hazırlamak için saatler harcıyor.
- **Çözüm:** AI destekli soru bankası ve sınav oluşturucu. Konuyu seç, zorluk belirle, otomatik sınav PDF'i oluştur.
- **Hedef müşteri:** Dershaneler, özel okullar, online eğitimciler
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Claude API, Supabase, PDF oluşturucu

---

## E-ticaret & Perakende

### 12. StoklarCanlı
- **Sektör:** E-ticaret & Perakende
- **Problem:** Birden fazla kanalda (Trendyol, Hepsiburada, kendi site) satan e-ticaret işletmeleri stok senkronizasyonunu yapamıyor.
- **Çözüm:** Merkezi stok yönetimi — bir kanalda satış olduğunda diğerlerinde stok otomatik güncellenir.
- **Hedef müşteri:** Çok kanallı e-ticaret satıcıları (aylık 100-5000 sipariş)
- **Fiyatlandırma:** $99/ay (1000 SKU'ya kadar), $199/ay (sınırsız)
- **Araçlar:** Claude Code, Supabase, n8n, Trendyol/Hepsiburada API

### 13. KargoTakipçi
- **Sektör:** E-ticaret & Perakende
- **Problem:** E-ticaret müşterileri sürekli "kargom nerede" diye soruyor, müşteri hizmetleri bununla boğuluyor.
- **Çözüm:** Otomatik kargo takip sayfası + WhatsApp bildirim sistemi. Kargo durumu değişince müşteriye anında haber gider.
- **Hedef müşteri:** Günlük 20+ kargo gönderen e-ticaret işletmeleri
- **Fiyatlandırma:** $49/ay (500 kargoya kadar), $99/ay (sınırsız)
- **Araçlar:** Claude Code, Supabase, n8n, kargo firma API'leri

### 14. İadeYönet
- **Sektör:** E-ticaret & Perakende
- **Problem:** İade süreçleri kaotik — müşteri ne için iade ettiği, ürünün durumu, geri ödeme takibi hep karışıyor.
- **Çözüm:** İade talebi portalı — müşteri fotoğraflı iade talebi açar, satıcı onaylar, kargo etiketi otomatik oluşur, geri ödeme takibi yapılır.
- **Hedef müşteri:** Kendi web sitesi olan e-ticaret markaları
- **Fiyatlandırma:** $59/ay
- **Araçlar:** Claude Code, Supabase, Stripe (geri ödeme), n8n

### 15. FiyatRadar
- **Sektör:** E-ticaret & Perakende
- **Problem:** Perakendeciler rakip fiyatlarını manuel takip ediyor, fiyat değişikliklerini kaçırıyor.
- **Çözüm:** Belirlenen rakip ürünlerinin fiyatlarını günlük takip edip, değişiklikleri raporlayan dashboard.
- **Hedef müşteri:** Online perakendeciler, marketplace satıcıları
- **Fiyatlandırma:** $79/ay (100 ürüne kadar)
- **Araçlar:** Claude Code, Supabase, n8n (scraping), Chart.js

### 16. YorumAsistan
- **Sektör:** E-ticaret & Perakende
- **Problem:** Marketplace satıcıları yüzlerce ürün yorumuna tek tek yanıt vermek zorunda, cevapsız kalınca puanları düşüyor.
- **Çözüm:** AI ile olumsuz yorumları tespit eden, otomatik yanıt taslağı oluşturan ve onay sonrası yayınlayan sistem.
- **Hedef müşteri:** Trendyol, Hepsiburada, Amazon satıcıları (100+ ürün)
- **Fiyatlandırma:** $49/ay
- **Araçlar:** Claude Code, Claude API, Supabase, n8n

### 17. TopluFatura
- **Sektör:** E-ticaret & Perakende
- **Problem:** Yüzlerce sipariş için tek tek e-fatura kesmek saatler sürüyor.
- **Çözüm:** Sipariş verilerini içeri aktarıp toplu e-fatura oluşturan ve e-arşiv sistemine gönderen otomasyon.
- **Hedef müşteri:** Günlük 50+ sipariş alan e-ticaret işletmeleri
- **Fiyatlandırma:** $69/ay
- **Araçlar:** Claude Code, n8n, Paraşüt/Logo API, Supabase

---

## Emlak & Gayrimenkul

### 18. GösterimPlan
- **Sektör:** Emlak & Gayrimenkul
- **Problem:** Emlakçılar gün boyu telefonla ev gösterim randevusu ayarlıyor, çakışmalar ve unutmalar oluyor.
- **Çözüm:** Online gösterim randevusu alma, otomatik hatırlatma, rota optimizasyonu (aynı bölgedeki gösterimleri sıralama).
- **Hedef müşteri:** Bireysel emlak danışmanları, küçük emlak ofisleri
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Supabase, Google Maps API, n8n

### 19. KiraTakip
- **Sektör:** Emlak & Gayrimenkul
- **Problem:** Birden fazla mülk sahibi olanlar kira ödemelerini, sözleşme yenilemelerini, bakım taleplerini takip edemiyor.
- **Çözüm:** Mülk portföy yönetimi — kira takibi, gecikme uyarısı, sözleşme bitiş hatırlatması, kiracı iletişim portalı.
- **Hedef müşteri:** 3+ mülk sahibi bireysel yatırımcılar, küçük gayrimenkul şirketleri
- **Fiyatlandırma:** $49/ay (10 mülke kadar), $99/ay (sınırsız)
- **Araçlar:** Claude Code, Supabase, Stripe, n8n

### 20. İlanAsistan
- **Sektör:** Emlak & Gayrimenkul
- **Problem:** Emlak ilanı yazmak zaman alıcı, her ilan için fotoğraf düzenleme ve açıklama hazırlama gerekiyor.
- **Çözüm:** Birkaç bilgi ve fotoğraf yükle, AI profesyonel ilan metni ve SEO-uyumlu açıklama oluştursun.
- **Hedef müşteri:** Emlak danışmanları, inşaat firmaları
- **Fiyatlandırma:** $29/ay
- **Araçlar:** Claude Code, Claude API, Supabase, Cloudflare R2

### 21. ApartmanYönet
- **Sektör:** Emlak & Gayrimenkul
- **Problem:** Apartman/site yöneticileri aidat takibini, gider raporlamasını ve duyuruları hala kağıt/WhatsApp grubu ile yapıyor.
- **Çözüm:** Online aidat takibi, otomatik hatırlatma, gider şeffaflığı, kat malikleri duyuru paneli.
- **Hedef müşteri:** Apartman yöneticileri, site yönetimleri (20-200 daire)
- **Fiyatlandırma:** $59/ay
- **Araçlar:** Claude Code, Supabase, Stripe/iyzico, n8n

### 22. EmlakCRM
- **Sektör:** Emlak & Gayrimenkul
- **Problem:** Emlakçılar müşteri takibini not defteri ve telefon rehberiyle yapıyor, potansiyel alıcıları kaybediyor.
- **Çözüm:** Emlağa özel basit CRM — müşteri tercihleri (bölge, bütçe, oda sayısı), otomatik eşleştirme, takip hatırlatmaları.
- **Hedef müşteri:** Bireysel emlak danışmanları, 2-5 kişilik emlak ofisleri
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Supabase, n8n, Resend

---

## Hukuk & Muhasebe

### 23. SözleşmeBankası
- **Sektör:** Hukuk & Muhasebe
- **Problem:** Küçük hukuk büroları her sözleşme için sıfırdan hazırlama yapıyor, şablon yönetimi kaotik.
- **Çözüm:** Sözleşme şablon kütüphanesi — değişkenleri doldur (isim, tarih, tutar), AI ile özelleştir, PDF olarak indir.
- **Hedef müşteri:** 1-5 avukatlı hukuk büroları, serbest avukatlar
- **Fiyatlandırma:** $49/ay
- **Araçlar:** Claude Code, Claude API, Supabase, PDF oluşturucu

### 24. DosyaTakip
- **Sektör:** Hukuk & Muhasebe
- **Problem:** Avukatlar dava dosyalarını, duruşma tarihlerini ve sürelerini takip etmekte zorlanıyor.
- **Çözüm:** Dava yönetim paneli — duruşma takvimi, süre takibi, otomatik hatırlatmalar, müvekkil portalı.
- **Hedef müşteri:** Serbest avukatlar, küçük hukuk büroları
- **Fiyatlandırma:** $59/ay
- **Araçlar:** Claude Code, Supabase, FullCalendar.js, n8n

### 25. MuhasebeKöprü
- **Sektör:** Hukuk & Muhasebe
- **Problem:** KOBİ'ler her ay muhasebecilerine belge göndermekte zorlanıyor — faturalar kayıp, dekontlar eksik.
- **Çözüm:** Müşteri fatura/dekont fotoğrafını çeker yükler, AI bilgileri çıkarır, muhasebeci panelinden erişir.
- **Hedef müşteri:** Serbest muhasebeciler (10-50 müşterili)
- **Fiyatlandırma:** $79/ay (muhasebeci başına, 30 müşteriye kadar)
- **Araçlar:** Claude Code, Claude API (OCR/veri çıkarma), Supabase, Cloudflare R2

### 26. VergiBildirim
- **Sektör:** Hukuk & Muhasebe
- **Problem:** Muhasebeciler vergi beyanname tarihlerini ve müşteri özel yükümlülüklerini takip etmekte zorlanıyor.
- **Çözüm:** Vergi takvimi + müşteri bazlı hatırlatma sistemi. Hangi müşterinin hangi beyannamesi ne zaman, otomatik bildirim.
- **Hedef müşteri:** Serbest muhasebeciler, mali müşavirler
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Supabase, n8n, Resend

### 27. TahsilatTakip
- **Sektör:** Hukuk & Muhasebe
- **Problem:** KOBİ'ler alacak takibini manuel yapıyor, vadesi geçen faturalar kaybolup gidiyor.
- **Çözüm:** Fatura vade takibi, otomatik hatırlatma e-postaları (nazik → ciddi → son uyarı dizisi), tahsilat raporu.
- **Hedef müşteri:** KOBİ'ler, serbest çalışanlar, ajanslar
- **Fiyatlandırma:** $49/ay
- **Araçlar:** Claude Code, Supabase, n8n, Resend

### 28. MasrafOnay
- **Sektör:** Hukuk & Muhasebe
- **Problem:** Şirketlerde çalışan masraf bildirimleri (taksi, yemek, konaklama) kağıt fiş ile takip ediliyor.
- **Çözüm:** Fişi fotoğrafla, AI bilgileri çıkarsın, yönetici onaylasın, ay sonunda otomatik rapor oluşsun.
- **Hedef müşteri:** 10-100 çalışanlı şirketler
- **Fiyatlandırma:** $99/ay (50 çalışana kadar)
- **Araçlar:** Claude Code, Claude API, Supabase, Cloudflare R2

---

## Restoran & Gıda

### 29. MenüDijital
- **Sektör:** Restoran & Gıda
- **Problem:** Basılı menüler pahalı, güncellenmesi zor, müşteriler QR kod beklentisi içinde.
- **Çözüm:** QR kodlu dijital menü — fotoğraflı, kategorili, fiyat güncelleme anında, çoklu dil desteği.
- **Hedef müşteri:** Kafeler, restoranlar, barlar
- **Fiyatlandırma:** $29/ay
- **Araçlar:** Claude Code, Supabase, Cloudflare R2, QR oluşturucu

### 30. SiparişAkış
- **Sektör:** Restoran & Gıda
- **Problem:** Küçük restoranlar paket servis siparişleri için Yemeksepeti'ne %25-35 komisyon ödüyor.
- **Çözüm:** Restoranın kendi online sipariş sayfası — WhatsApp bildirimi, basit mutfak ekranı, komisyonsuz.
- **Hedef müşteri:** Mahalle restoranları, pizza/burger dükkanları, pastaneler
- **Fiyatlandırma:** $49/ay
- **Araçlar:** Claude Code, Supabase, WhatsApp Business API, iyzico

### 31. StokSayım
- **Sektör:** Restoran & Gıda
- **Problem:** Restoran mutfak stok sayımı haftada 2-3 saat sürüyor, hep kağıt üzerinde.
- **Çözüm:** Mobil stok sayım uygulaması — barkod okut veya listeden seç, adet gir, otomatik sipariş önerisi.
- **Hedef müşteri:** Restoranlar, kafeler, catering firmaları
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Supabase, PWA (kamera erişimi)

### 32. PersonelVardiya
- **Sektör:** Restoran & Gıda
- **Problem:** Restoran müdürleri vardiya planlamasını her hafta Excel'de yapıp WhatsApp'tan paylaşıyor, değişiklikler kaos yaratıyor.
- **Çözüm:** Online vardiya planlama — personel müsaitliği, otomatik denge, değişiklik bildirimi, fazla mesai hesaplama.
- **Hedef müşteri:** 10-50 personelli restoranlar, kafe zincirleri
- **Fiyatlandırma:** $59/ay
- **Araçlar:** Claude Code, Supabase, n8n, PWA

### 33. MüşteriBağla
- **Sektör:** Restoran & Gıda
- **Problem:** Restoranlar sadık müşterilerini tanımıyor, tekrar gelmelerini teşvik eden bir sistemi yok.
- **Çözüm:** Dijital sadakat kartı — QR ile puan toplama, X. siparişte Y hediye, doğum günü kampanyaları.
- **Hedef müşteri:** Kafeler, fast-food zincirleri, pastaneler
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Supabase, QR oluşturucu, n8n

### 34. GıdaGüvenlik
- **Sektör:** Restoran & Gıda
- **Problem:** Gıda güvenliği denetimleri için gereken sıcaklık ölçüm kayıtları, temizlik çizelgeleri hep kağıtta kalıyor.
- **Çözüm:** Dijital HACCP/gıda güvenliği checklist sistemi — günlük kontroller, fotoğraflı kayıt, denetim raporu oluşturma.
- **Hedef müşteri:** Restoran zincirleri, catering firmaları, otel mutfakları
- **Fiyatlandırma:** $49/ay (lokasyon başına)
- **Araçlar:** Claude Code, Supabase, Cloudflare R2, PDF oluşturucu

---

## Fitness & Spor

### 35. ÜyelikPro
- **Sektör:** Fitness & Spor
- **Problem:** Küçük spor salonları üyelik takibini kağıt defter veya basit Excel ile yapıyor, kimler aktif bilemiyorlar.
- **Çözüm:** Üyelik yönetimi — kayıt, süre takibi, otomatik yenileme hatırlatması, giriş-çıkış kaydı (QR ile).
- **Hedef müşteri:** Bağımsız spor salonları, pilates/yoga stüdyoları
- **Fiyatlandırma:** $49/ay (100 üyeye kadar), $89/ay (sınırsız)
- **Araçlar:** Claude Code, Supabase, QR oluşturucu, Stripe/iyzico

### 36. AntrenmanPlan
- **Sektör:** Fitness & Spor
- **Problem:** PT'ler (personal trainer) her müşteriye özel antrenman programı hazırlamak için saatler harcıyor.
- **Çözüm:** AI destekli antrenman planı oluşturucu — müşteri hedefi, seviyesi, ekipmanı gir, kişiselleştirilmiş program çıksın.
- **Hedef müşteri:** Personal trainer'lar, online fitness koçları
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Claude API, Supabase

### 37. DersRezervAsyon
- **Sektör:** Fitness & Spor
- **Problem:** Yoga/pilates stüdyolarında ders kontenjanları doluyor ama iptal/no-show yüzünden boş kalıyor.
- **Çözüm:** Online ders rezervasyonu — kontenjan takibi, bekleme listesi, otomatik iptal doldurma, no-show cezası.
- **Hedef müşteri:** Yoga, pilates, dans stüdyoları, boks salonları
- **Fiyatlandırma:** $49/ay
- **Araçlar:** Claude Code, Supabase, Stripe/iyzico, n8n

### 38. VücutTakip
- **Sektör:** Fitness & Spor
- **Problem:** Üyeler ilerlemelerini göremeyince motivasyonlarını kaybedip salondan ayrılıyor.
- **Çözüm:** Üye ilerleme takibi — ölçüm kayıtları, fotoğraflı karşılaştırma, grafik raporlar, PT ile paylaşım.
- **Hedef müşteri:** Spor salonları, PT'ler, diyet klinikleri
- **Fiyatlandırma:** $29/ay
- **Araçlar:** Claude Code, Supabase, Chart.js, Cloudflare R2

### 39. TurnuvOrganizatör
- **Sektör:** Fitness & Spor
- **Problem:** Halı saha, tenis kulübü gibi yerler turnuva organizasyonunu tamamen manuel yapıyor.
- **Çözüm:** Turnuva yönetimi — kayıt formu, otomatik fikstür oluşturma, skor girişi, canlı puan tablosu.
- **Hedef müşteri:** Halı saha işletmeleri, tenis/padel kulüpleri, amatör lig organizatörleri
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Supabase, PWA

### 40. SporcuBeslenme
- **Sektör:** Fitness & Spor
- **Problem:** Diyetisyen ve beslenme koçları müşterilerine beslenme programı gönderiyor ama takip edemiyor.
- **Çözüm:** Beslenme planı paylaşımı + müşterinin günlük öğün fotoğrafı yükleyip koçun geri bildirim verdiği portal.
- **Hedef müşteri:** Online diyetisyenler, beslenme koçları
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Supabase, Cloudflare R2, PWA

---

## Dijital Ajanslar

### 41. MüşteriPortal
- **Sektör:** Dijital Ajanslar
- **Problem:** Ajanslar müşterilerine proje durumunu WhatsApp ve mail ile anlatmaya çalışıyor, sürekli "ne aşamada" sorusu geliyor.
- **Çözüm:** Müşteriye özel portal — proje durumu, onay bekleyen görevler, dosya paylaşımı, fatura geçmişi, canlı durum takibi.
- **Hedef müşteri:** 5-30 müşterili dijital ajanslar, freelancer'lar
- **Fiyatlandırma:** $79/ay (20 müşteriye kadar)
- **Araçlar:** Claude Code, Supabase, Cloudflare R2, Stripe

### 42. İçerikTakvim
- **Sektör:** Dijital Ajanslar
- **Problem:** Sosyal medya ajansları içerik takvimini Google Sheets'te yönetiyor, onay süreci karmaşık.
- **Çözüm:** Görsel içerik takvimi — drag & drop planlama, müşteri onay akışı, tek tıkla yayınlama hatırlatması.
- **Hedef müşteri:** Sosyal medya ajansları, içerik üreticileri
- **Fiyatlandırma:** $49/ay (marka başına)
- **Araçlar:** Claude Code, Supabase, Cloudflare R2

### 43. RaporOtomatik
- **Sektör:** Dijital Ajanslar
- **Problem:** Ajanslar her ay müşteri raporlarını hazırlamak için 2-3 saat harcıyor — veriyi topla, düzenle, sunuma çevir.
- **Çözüm:** Google Analytics, Meta Ads, Google Ads verilerini çekip otomatik aylık rapor PDF oluşturan sistem.
- **Hedef müşteri:** Dijital pazarlama ajansları
- **Fiyatlandırma:** $99/ay (10 müşteriye kadar)
- **Araçlar:** Claude Code, n8n, Google Analytics API, Meta API, PDF oluşturucu

### 44. TeklifHazırla
- **Sektör:** Dijital Ajanslar
- **Problem:** Her yeni proje için sıfırdan teklif hazırlamak saatler sürüyor, standart bir format yok.
- **Çözüm:** Teklif şablon sistemi — proje tipi seç, kapsamı belirle, AI fiyat ve süre önerisi yapsın, profesyonel PDF çıksın.
- **Hedef müşteri:** Freelancer yazılımcılar, dijital ajanslar, tasarım stüdyoları
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Claude API, Supabase, PDF oluşturucu

### 45. SEOİzle
- **Sektör:** Dijital Ajanslar
- **Problem:** SEO ajansları müşteri keyword sıralamalarını takip etmek için pahalı araçlar (Ahrefs, Semrush) kullanmak zorunda.
- **Çözüm:** Temel keyword sıralama takibi — günlük/haftalık sıra değişimi, grafik raporlar, müşteriye otomatik bildirim.
- **Hedef müşteri:** Küçük SEO ajansları, freelancer SEO uzmanları
- **Fiyatlandırma:** $59/ay (100 keyword'e kadar)
- **Araçlar:** Claude Code, Supabase, Google Search Console API, Chart.js

### 46. FormYönetici
- **Sektör:** Dijital Ajanslar
- **Problem:** Ajanslar her müşteri sitesine ayrı form çözümü kuruyor, leadleri toplamak dağınık.
- **Çözüm:** Merkezi form builder — embed kodu ile herhangi bir siteye ekle, tüm leadler tek panelde, webhook ile CRM'e aktar.
- **Hedef müşteri:** Web geliştirme ajansları, freelancer'lar
- **Fiyatlandırma:** $39/ay
- **Araçlar:** Claude Code, Supabase, n8n (webhook)

### 47. MüşteriOnboard
- **Sektör:** Dijital Ajanslar
- **Problem:** Yeni müşteri başlangıcında gerekli bilgileri (logo, erişim bilgileri, marka rehberi) toplamak haftalar sürüyor.
- **Çözüm:** Otomatik onboarding akışı — müşteriye adım adım form gönder, dosya toplama, erişim bilgisi isteme, tamamlanma takibi.
- **Hedef müşteri:** Dijital ajanslar, freelancer'lar
- **Fiyatlandırma:** $29/ay
- **Araçlar:** Claude Code, Supabase, Cloudflare R2, n8n

### 48. WebSiteSağlık
- **Sektör:** Dijital Ajanslar
- **Problem:** Ajansların yönettiği müşteri siteleri çökünce saatler sonra fark ediyorlar.
- **Çözüm:** Uptime monitoring + sayfa hız testi + SSL sertifika takibi. Sorun olunca anında bildirim.
- **Hedef müşteri:** Web geliştirme ajansları, hosting sağlayıcıları
- **Fiyatlandırma:** $29/ay (20 siteye kadar)
- **Araçlar:** Claude Code, Supabase, n8n (cron), Resend

### 49. ChatBotKur
- **Sektör:** Dijital Ajanslar
- **Problem:** Müşteriler 7/24 canlı destek istiyor ama küçük işletmelerin buna bütçesi yok.
- **Çözüm:** No-code AI chatbot oluşturucu — işletmenin SSS ve bilgilerini yükle, web sitesine embed et, müşteri sorularını otomatik yanıtlasın.
- **Hedef müşteri:** Dijital ajanslar (müşterilerine hizmet olarak sunar)
- **Fiyatlandırma:** $79/ay (bot başına), $199/ay (5 bot)
- **Araçlar:** Claude Code, Claude API, Supabase, web widget

### 50. FreelancerFatura
- **Sektör:** Dijital Ajanslar
- **Problem:** Freelancer'lar fatura oluşturma, gönderme ve ödeme takibini farklı araçlarla yapıyor.
- **Çözüm:** Tek panelden profesyonel fatura oluştur, e-posta ile gönder, ödeme takibi yap, aylık gelir raporu al.
- **Hedef müşteri:** Freelancer yazılımcılar, tasarımcılar, danışmanlar
- **Fiyatlandırma:** $19/ay
- **Araçlar:** Claude Code, Supabase, Stripe, Resend, PDF oluşturucu

---

## Nasıl Kullanılır?

1. **İlgi alanını seç** — Hangi sektörü biliyorsun veya hangi sektördeki insanlara erişimin var?
2. **Problemi doğrula** — O sektördeki 5-10 işletmeyle konuş. Gerçekten bu problemi yaşıyorlar mı?
3. **MVP kur** — Claude Code ile 2 haftada çalışan bir versiyon çıkar.
4. **İlk müşteriyi bul** — Konuştuğun işletmelere göster, beta kullanıcı olarak başlat.
5. **Iterate et** — Geri bildirimlere göre geliştir, fiyatlandırmayı test et.

> Mükemmel ürün çıkarmaya çalışma. Çalışan ürün çıkar, sonra mükemmelleştir.
