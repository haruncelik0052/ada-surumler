# ADA sürümleri

Bu depo **yalnız dağıtım içindir**: ADA uygulamalarının imzalı APK ve `.adaguncelleme` dosyaları [Releases](../../releases) bölümünde yayınlanır. Kaynak kod gizli depolardadır; burada kaynak kod yoktur.

| Uygulama | Paket | Etiket |
|---|---|---|
| AdaOctopus (Deneysel) | `app.adasistem.deneysel.octopus` | `octopus-k<kod>` |
| TeklifX (Deneysel) | `app.adasistem.deneysel.teklifx` | `teklifx-k<kod>` |

## Güvenlik
- Her APK aynı imza sertifikasıyla imzalıdır (SHA-256 `0d88a7e3e5e73d019aed029c205f61dc8ef77ae26ec9f2e3906ebb2e5f872ec7`). Android, farklı imzalı bir dosyayı mevcut uygulamanın üzerine kurmaz.
- `.adaguncelleme` paketleri ayrıca ADA güncelleme anahtarıyla (ECDSA P-256) imzalıdır; uygulama indirdiği paketi kurmadan önce imzayı, paket adını, sürümü, APK özetini ve sertifikayı denetler.
- Uygulamalar bu depodan **erişim anahtarı olmadan** yeni sürümü bulur ve indirir; kurulum Android'in "Yükle" onayıyla yapılır.

## Nasıl yayınlanır
Gizli derleme hattı (GitHub Actions) yalnız bu depoya yazabilen bir deploy key ile dosyaları geçici `gelen/<etiket>` dalına gönderir. `.github/workflows/yayinla.yml` dosyaları denetler (izinli dosya türleri, SHA-256 listesi), Release oluşturur ve geçici dalı siler.
