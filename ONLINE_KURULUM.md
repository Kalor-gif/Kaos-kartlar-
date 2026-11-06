# Kaos Kartları — Online oda kurulumu

## Gerekenler
- Ücretsiz bir Supabase projesi
- Supabase Project URL
- Supabase anon / publishable key

**Service role key kullanmayın.** Bu anahtar gizlidir ve tarayıcıya konmamalıdır.

## Supabase ayarları
1. https://supabase.com adresinden giriş yapıp yeni bir proje oluşturun.
2. Proje açıldıktan sonra Project Settings → API bölümüne girin.
3. Project URL ve anon/public (publishable) key değerlerini alın.
4. Projede Realtime özelliğinin etkin olduğundan emin olun. Uygulama Supabase Realtime Presence ve Broadcast kanallarını kullanır; oda/oyuncu tablosu veya SQL migration gerektirmez.

## Oyunda bağlantı
1. Kaos Kartları'nı açın.
2. Ayarlar → Online oda bağlantısı alanına Project URL ve anon/publishable key bilgilerini girin.
3. Bağlantıyı kaydedin. Aynı Supabase bilgilerini oyuna katılacak diğer telefonlarda da kaydedin.
4. Bir telefonda Ana Menü → Oda Oluştur seçin.
5. Beş karakterli oda kodunu arkadaşlarınıza gönderin.
6. Diğer oyuncular kendi telefonlarından Odaya Katıl seçip adlarını ve kodu girsin.
7. En az 5 oyuncu bağlandığında oda kurucusu Oyunu Başlat düğmesine bassın.

## Mevcut online oyun kapsamı
Şu an oda kurucusunun ekranı ve tur aksiyonları Supabase Broadcast ile diğer cihazlara aktarılır. Online oda akışı Yasaklı Kelime moduna sabitlenmiştir. Diğer modlar (Gizli Kelime, Kim Yazdı?, Çizdim Bozdum ve Son 5 Saniye) online çoklu cihaz senkronizasyonu için henüz tamamlanmamıştır.

## Güvenlik ve test
- Oda kodu tek başına güçlü kimlik doğrulama değildir; hassas veri paylaşmayın.
- Supabase anon/publishable key tarayıcıda kullanılmak üzere tasarlanmıştır; service role key asla paylaşılmamalıdır.
- Yayına çıkmadan önce 5–10 ayrı cihaz/oturumla oda oluşturma, katılma, bağlantı kopması ve tur senkronizasyonu test edilmelidir.
