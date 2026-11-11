# SHIELD SYSTEM — PWA yayınlama

Bu proje, Google AI Studio'dan dışa aktarılan React + TypeScript + Vite uygulamasıdır. PWA için web manifesti, uygulama simgeleri ve temel çevrimdışı uygulama kabuğu eklendi. Oyun özellikleri ve mevcut `localStorage` kayıt mekanizması değiştirilmedi.

## Ücretsiz Cloudflare Pages yayınlama

1. Bu ZIP'i bilgisayarında bir klasöre çıkar.
2. Klasörün içindeki proje dosyalarını bir GitHub deposuna yükle (ZIP dosyasını değil, ZIP'in içeriğini).
3. Cloudflare Dashboard → Workers & Pages → Create application → Pages → Connect to Git bölümünden GitHub deposunu bağla.
4. Build ayarları:
   - Framework preset: **Vite**
   - Build command: **npm run build**
   - Build output directory: **dist**
   - Root directory: **/** (boş bırakılabilir)
5. Deploy ile yayınla. Ücretsiz `*.pages.dev` adresi verilir.
6. Site HTTPS üzerinden açıldıktan sonra Android Chrome menüsünden **Uygulamayı yükle** veya **Ana ekrana ekle** seçeneğini kullan.

## Önemli

- Cloudflare Pages statik barındırma için ücretsiz plan sunar; özel alan adı almak zorunlu değildir.
- Bu kaynak ZIP'i Cloudflare Pages'in **Direct Upload** alanına doğrudan yüklenemez. Önce Vite derlemesi gerekir; Git bağlantılı Pages bunu otomatik yapar.
- İlk yüklemede internet gerekir. Daha önce açılmış sayfaların ve yüklenen dosyaların çevrimdışı kullanılabilmesi için temel service worker önbelleği eklidir; tüm harici servislerin çevrimdışı çalışacağı garanti edilmez.
- Oyun kayıtları bu sürümde tarayıcının `localStorage` alanında tutulur. Tarayıcı verileri temizlenirse veya farklı cihaz/tarayıcı kullanılırsa kayıtlar otomatik eşitlenmez. Ayarlar bölümündeki dışa/içe aktarma işlevini kullanarak yedek alın.
- Bu projede derleme, bu çalışma ortamında paket deposuna erişim zaman aşımına uğradığı için burada çalıştırılıp doğrulanamadı. Cloudflare'ın derleme logunu kontrol etmeden yayını hatasız diye kabul etme.
