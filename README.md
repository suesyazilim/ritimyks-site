# Ritim — tanıtım sitesi

Sade, derleme gerektirmeyen statik site: `index.html`, `privacy/`, `terms/`, `assets/`.

## Yayına alma (alan adını aldıktan sonra)

En kolay yol **GitHub Pages** veya **Cloudflare Pages** (ikisi de ücretsiz):

1. Bu `website/` klasörünün içeriğini bir GitHub deposuna koy (kökte `index.html` olacak şekilde).
2. GitHub → Settings → Pages → "Deploy from a branch" → `main` / root.
3. Alan adını Settings → Pages → Custom domain'e yaz; alan adı firmasında GitHub'ın gösterdiği DNS kayıtlarını ekle. "Enforce HTTPS" açık olsun.

## Yayından önce değiştirilecekler

- **Mağaza linkleri:** `index.html` en alttaki `STORE_LINKS` içine Play Store / App Store linklerini yaz. Boş olan "Yakında" görünür.
- **Uygulamadaki linkler:** Paywall'daki `https://ritimyks.com/terms` ve `/privacy` adresleri yeni alan adınla değişmeli (Android: `PaywallScreen.kt`). Bu site o yolları (`/privacy/`, `/terms/`) aynen sunuyor.
- **Play Console:** Gizlilik politikası URL'si olarak `https://<alan-adın>/privacy/` gir.

## İsim değişirse

Görünen ad "Ritim" ve "YKS Koçu" metinlerinde geçiyor. Tek komutla:

```bash
grep -rl "Ritim" . | xargs sed -i '' 's/Ritim/YeniAd/g'
```

Sonra `assets/img/og.jpg` (paylaşım görseli) ve ekran görüntülerini yeniden üret.

## Görseller

- `assets/img/*.jpg` — sitedeki telefon ekranları (örnek öğrenci verisiyle, emülatörden).
- Play Store için tam çözünürlüklü ekranlar: depo kökündeki `store-assets/`.
