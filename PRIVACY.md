# Gizlilik / Privacy

*Son güncelleme / Last updated: 2026-11-20*

**Geliştirici / Developer:** Furkan Avcılar · statelyxx@gmail.com · +90 538 652 53 03 · https://github.com/statelyx

## Türkçe

PS Subtitle Translate Bridge, Furkan Avcılar tarafından geliştirilen ve AGPL-3.0 altında yayımlanan açık kaynaklı bir uygulamadır. Kayıt istemez, sizi uygulamalar arasında izlemez, üçüncü taraf reklam ağı ya da reklam SDK'sı kullanmaz; IDFA ve AAID toplanmaz. Uygulamada ve sitede yalnız geliştiricinin kendi ürünlerini tanıtan görseller ve sponsor bağlantıları çıkabilir; görseller kendi sunucumuzdan (`couchsubs.enmeraapps.com/promo.json`) indirilir, ne zaman gösterildiği yalnız cihazda tutulur ve dokununca bağlantı tarayıcıda açılır.

Dışarıya çıkan tek şey, kapatılabilen ortak havuza giden İngilizce oyun satırlarıdır (aşağıda). Bunun dışında kalan her şey cihazınızda ya da ev ağınızda kalır. Bilgisayar ve TV sürümleri kişisel veri toplamaz, reklam/analiz/izleme kodu içermez. Telefon sürümlerinin kimliğe bağlanmayan kullanım ölçümleri için "iPhone uygulaması" ve "Android uygulaması" bölümlerine bakın.

**Kısa özet**

- PS5'ten gelen görüntü yalnız altyazıyı okumak için bellekte işlenir; kaydedilmez, yüklenmez.
- Okunan satırlar ve çevirileri cihazda üretilir; yalnız ev ağınızdaki TV'ye ya da telefona gider.
- Ortak havuz kapatılabilir; kapatınca gönderim anında durur.
- Çevrimiçi çeviri motorları yalnız siz açarsanız devreye girer.

**Cihazda kalanlar**

- PS5 bağlantısı, eşleme anahtarları ve sayısal PlayStation Network hesap kimliği cihazda saklanır: iOS/macOS'ta Anahtar Zinciri'nde, Windows'ta kullanıcı hesabınıza bağlı DPAPI şifreli dosyada, Android'de Android Keystore anahtarıyla şifreli olarak, Linux'ta yalnız sahibinin okuyabildiği anahtar dosyasında.
- Girdiğiniz çeviri servisi anahtarları (Gemini, DeepL, OpenAI, Claude) aynı yerlerde tutulur.
- Altyazı bölgesi, dil, hedef (TV/telefon) gibi ayarlar cihazda kalır.
- Android'de bu veriler uygulamayla birlikte silinir ve yedeğe alınmaz.

**Dışarıyla kurulan bağlantılar**

- **Sony:** PlayStation Network girişi Sony'nin kendi sayfasında yapılır; şifrenizi uygulama görmez. Girişten sonra Sony'den yalnız sayısal hesap kimliği istenir, oturum anahtarı saklanmaz.
- **Model indirme (yalnız Windows ve Linux):** yazı tanıma ve çeviri modelleri ilk kullanımda bir kez `huggingface.co` adresinden indirilir ve SHA-256 ile doğrulanır.
- **Apple (yalnız Mac/iOS):** çeviri dilleri Apple tarafından indirilir ve yönetilir.
- **Google ML Kit (yalnız Android):** ücretsiz çeviri cihazda çalışır; Türkçe dil modeli ilk kullanımda bir kez Google'dan iner. ML Kit kendi çalışmasına dair performans ölçümlerini Google'a gönderebilir; satır metni ve görüntü buna dahil değildir.
- **Çevrimiçi çeviri (yalnız siz seçerseniz):** kendi anahtarınızla DeepL, Gemini, OpenAI ya da Claude'u açarsanız okunan İngilizce satır ve bağlam için son birkaç satır doğrudan o servise gider. Görüntü, ses ve hesap bilgisi gitmez; o servisin kendi gizlilik koşulları geçerlidir.
- **Ev ağı:** PS5 ve TV'yi bulmak, eşleşmek ve altyazı göndermek için yalnız yerel ağ kullanılır. Linux sürümü kurulum panelini yerel ağda 8788, telefon sürümü altyazı sunucusunu 8787 portunda açar.

**Ortak havuz (Ayarlar'dan kapatılabilir)**

Hiçbir hazır pakette bulunmayan, okunan İngilizce satırlar herkes için daha iyi Türkçe yamalar üretmek üzere `couchsubs-pool.enmera.workers.dev` adresine gider. Giden: satırın metni, ondan üretilen anahtar, ilk görüldüğü an, uygulama sürümü, işletim sistemi (ios/android/mac/windows/linux) ve kuruluma özgü rastgele bir kimlik. Biliniyorsa oynanan oyunun kimliği ve adı (ör. PPSA01234) da eklenir; oyunu PS5 bildirir, uygulama satırları hazır paketlerle eşleştirerek tanır ya da siz seçersiniz. En az iki farklı kurulumda görülen satırlar her gece makine çevirisiyle o oyunun yamasına dönüşür ve herkese dağıtılır; yamada satırı kimin gönderdiği yazmaz. Görüntü, ses, kullanıcı adı ve PSN bilgisi gönderilmez. Kapatınca gönderim durur ve bekleyen satırlar silinir.

**iPhone uygulaması**

- Reklam yok, izleme yok, hesap yok. Apple'ın izleme izni (ATT) istenmez, IDFA toplanmaz, veriler başka şirketlerin verileriyle birleştirilmez.
- Ana ekranda, boştayken, günde en çok bir kez kendi ürün tanıtım görselimiz çıkabilir; görsel kimlik bilgisi gönderilmeden indirilir, gösterim ve tıklama hiçbir yere bildirilmez.
- Kullanım ölçümü (Profil › Kullanım verisi'nden kapatılabilir) Google Firebase Analytics ve Meta App Events ile kimliğe bağlanmadan yapılır; çökmeler Firebase Crashlytics'e gider. Giden: çevirinin başlaması ve süresi, altyazının nerede gösterildiği (TV/telefon), bağlanan TV'nin markası, paketten gelen satır sayısı, güncellenen paket sayısı, açılan ekranlar, bu servislerin uygulamaya özgü rastgele kimliği, cihaz modeli, iOS sürümü ve IP'den çıkan ülke. Meta'ya yalnız olay adları ve uygulama açılışı gider. Satır metni, görüntü, PSN hesabı ve anahtarlar gitmez. Google'ın ve Meta'nın kendi koşulları geçerlidir.
- Ortak havuz Profil'den kapatılabilir. Paketler kimlik bilgisi gönderilmeden indirilir.

**Android uygulaması**

- Reklam ağı/SDK yok, hesap yok; Android Advertising ID toplanmaz, ilgili izinler uygulamada bulunmaz.
- PS5'e yalnız aynı Wi-Fi üzerinden Uzaktan Oynatma ile bağlanılır. Görüntü cihaz belleğinde, cihaz üstünde (Google ML Kit yazı tanıma) işlenir; kaydedilmez, yüklenmez. Çeviri sürerken kalıcı bildirim görünür.
- PSN girişi Sony'nin sayfasında yapılır; şifre yalnız Sony'ye gider, oturum anahtarı saklanmaz.
- Kullanım ölçümü varsayılan açıktır, Profil › Kullanım verisi'nden kapatılır; kapatınca Firebase ve Meta'ya hiçbir şey gitmez. Giden alanlar iPhone bölümündekiyle aynıdır; ayrıca seçilen hedef, çeviri motoru, paketlerin açık olup olmadığı ve kullanılan paketin adı eklenir.
- Ortak havuz varsayılan açıktır (Ayarlar › Ortak havuza katkı), işletim sistemi "android" olarak gider.
- TV'de gösterim için telefon yerel ağda küçük bir sunucu açar; altyazılar yalnız aynı ağdaki TV uygulamasına gider.

**Windows, Mac ve Linux sürümleri**

- Görüntü yalnız altyazıyı okumak için bellekte işlenir; kaydedilmez, yüklenmez.
- Çeviri cihazda üretilir (Windows'ta yerel model, Mac'te sistem çevirisi, Linux'ta Tesseract ile okuma ve isteğe bağlı çevrimiçi motor). Yalnız ev ağınızdaki TV'ye gönderilir.
- Windows'ta isteğe bağlı gelişmiş yazı tanıma açılırsa PP-OCRv6 modelleri ilk seçişte bir kez Hugging Face'ten iner.
- Linux sürümü Docker ile çalışır ve kurulum/denetim için yerel ağda bir tarayıcı paneli açar.

**TV uygulamaları (webOS, Tizen, Android TV)**

Altyazıyı yalnız ev ağındaki köprü cihazdan alır; internete bağlanmaz, kişisel veri toplamaz.

**Haklarınız ve iletişim**

Cihazdaki veriler uygulamayı silince gider. Ortak havuza gönderilmiş satırlarda size ait bir kimlik bulunmadığı için silinecek kişisel kayıt yoktur.

Sorular, hata bildirimleri ve silme talepleri:

- E-posta: statelyxx@gmail.com
- Telefon: +90 538 652 53 03
- GitHub: https://github.com/statelyx
- Hata kaydı: https://github.com/statelyx/PS5-Turkce-Ceviri/issues

Sony Interactive Entertainment ile resmî bağlantı yoktur.

## English

PS Subtitle Translate Bridge is open-source software by Furkan Avcılar, released under AGPL-3.0. There is no sign-up, no cross-app tracking, no third-party ad network and no ad SDK; IDFA and AAID are never collected. The app and the site may only show images promoting the developer's own products and sponsor links; those images come from our server (`couchsubs.enmeraapps.com/promo.json`), the display counter lives on the device, and a tap opens the link in your browser.

The only outbound traffic is English game text heading to the shared pool, which you can switch off (below). Everything else stays on your device or your home network. The desktop and TV builds collect no personal data and contain no ad, analytics or tracking code. For the unlinked usage metrics of the phone builds, see "iPhone app" and "Android app".

**In short**

- The PS5 picture is processed in memory only to read subtitles; nothing is stored or uploaded.
- Lines and translations are produced on the device and go only to your TV or phone on the local network.
- The shared pool can be turned off, and sending stops instantly.
- Online translation engines engage only if you enable them.

**What stays on the device**

- The PS5 pairing keys and the numeric PlayStation Network account ID are kept locally: Keychain on iOS/macOS, a DPAPI file bound to your Windows user account, an Android Keystore-encrypted store on Android, and an owner-readable key file on Linux.
- Any translation service keys you enter (Gemini, DeepL, OpenAI, Claude) are stored the same way.
- Subtitle region, language and output target (TV or phone) stay on the device.
- On Android this data is deleted with the app and is not included in backups.

**External connections**

- **Sony:** PlayStation Network sign-in runs on Sony's own page and the app never sees your password. Only the numeric account ID is fetched afterwards; no session token is retained.
- **Model downloads (Windows and Linux only):** OCR and translation models are fetched once from `huggingface.co` and verified by SHA-256.
- **Apple (Mac/iOS only):** translation languages are downloaded and managed by Apple.
- **Google ML Kit (Android only):** free translation runs on-device; the Turkish model is downloaded once from Google. ML Kit may report its own performance metrics to Google, without line text or pictures.
- **Online translation (only if you enable it):** with your own key, DeepL, Gemini, OpenAI or Claude receives the English line and the last few lines for context directly. No picture, audio or account data; that service's own privacy terms apply.
- **Home network:** discovery, pairing and subtitle delivery use the local network only. The Linux build exposes its setup panel on port 8788, the phone build runs a subtitle server on port 8787.

**Shared pool (switchable in Settings)**

English lines that appear in no ready-made pack go to `couchsubs-pool.enmera.workers.dev` so that better Turkish packs can be produced for everyone. Sent: the line text, a key derived from it, the moment it was first seen, app version, operating system (ios/android/mac/windows/linux) and a random per-installation ID. When known, the game ID and name (e.g. PPSA01234) are attached: the PS5 reports it, the app matches lines against packs, or you pick it. Lines seen by at least two installations are machine-translated every night into that game's pack and distributed; the pack carries no sender information. No picture, audio, user name or PSN data. Turning it off stops sending and deletes queued lines.

**iPhone app**

- No ads, no tracking, no account. App Tracking Transparency is never requested, IDFA is never collected, and data is not joined with other companies' data.
- The idle home screen may show one of our own promo images at most once a day; it is downloaded without identifiers and views or taps are not reported.
- Usage metrics (Profile › Usage data, switchable) use Google Firebase Analytics and Meta App Events without linking to you; crashes go to Firebase Crashlytics. Sent: translation start and duration, where subtitles are shown (TV or phone), connected TV brand, lines taken from packs, packs updated, screens opened, plus the services' random app-specific ID, device model, iOS version and IP-derived country. Meta only gets event names and app launches. No line text, picture, PSN account or keys. Google's and Meta's own terms apply.
- The shared pool is switchable in Profile. Packs download without identifiers.

**Android app**

- No ad network or SDK, no account; the Android Advertising ID is not collected and the related permissions are absent.
- The phone reaches the PS5 only over the same Wi-Fi using Remote Play. Frames are processed in device memory on-device (Google ML Kit OCR); nothing is stored or uploaded. A persistent notification shows while translation runs.
- PSN sign-in happens on Sony's page; your password goes only to Sony and no session token is kept.
- Usage metrics are on by default and switch off in Profile › Usage data; once off, nothing goes to Firebase or Meta. Fields match the iPhone section, plus the chosen target, translation engine, whether packs are enabled and the pack name.
- The shared pool is on by default (Settings › Contribute to the shared pool) and reports the OS as "android".
- For TV output the phone runs a small local server; subtitles reach only the TV app on the same network.

**Windows, Mac and Linux builds**

- The picture is processed in memory only to read subtitles; nothing is stored or uploaded.
- Translation is produced on the device (local model on Windows, system translation on Mac, Tesseract reading plus optional online engines on Linux) and sent only to your TV on the home network.
- Optional advanced OCR on Windows downloads the PP-OCRv6 models once from Hugging Face on first selection.
- The Linux build runs in Docker and serves a setup panel on the local network.

**TV apps (webOS, Tizen, Android TV)**

They take subtitles only from the bridge on the home network, never connect to the internet and collect no personal data.

**Your rights and contact**

Device data disappears with the app. Shared-pool lines carry no identity, so there is no personal record to erase there.

Questions, bug reports and deletion requests:

- Email: statelyxx@gmail.com
- Phone: +90 538 652 53 03
- GitHub: https://github.com/statelyx
- Issue tracker: https://github.com/statelyx/PS5-Turkce-Ceviri/issues

Not affiliated with Sony Interactive Entertainment.
