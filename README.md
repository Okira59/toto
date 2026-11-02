# Spor Toto — 15 maç tahmin ve sistem kuponları

`Okira59/Pyhton` deposundaki `toto/` klasöründen (commit geçmişiyle birlikte) taşındı.

`toto.py`, haftanın Spor Toto programını (15 maç) iddaa'dan alır; Bet365 / William Hill oranlarından
marjı temizlenmiş 1-0-2 olasılıklarını hesaplar (`calib.json` kalibrasyonu ile), eksik oyuncu, hava durumu,
form/H2H ve uzman yorumlarını bilgi olarak ekler, farklı kolon bütçeleri için 15/15 olasılığını en yükselten
sistem kuponlarını üretir ve geçmiş haftaları sonuçlandırır.

| Dosya | İçerik |
|---|---|
| `toto.py` | Analiz + kupon scripti |
| `calib.json` | Olasılık kalibrasyonu (güç `a`, beraberlik kaydırması `d`) |
| `data/state.json` | Son çalışma durumu |
| `data/kadro.json` | Oyuncu maç/ilk 11 sayıları önbelleği |
| `data/yorum.json` | Çevrilmiş maç önizlemeleri önbelleği |
| `data/geo.json` | Stadyum konumları (hava durumu için) |
| `gol/` | `Okira59/gol` modüllerinin kopyası |
| `docs/` | Panel (PWA) ve `docs/data/` çıktıları |

## Kurulum
```bash
pip install -r requirements.txt
```

## Çalıştırma
```bash
python toto.py       # -> docs/data/toto.json, docs/data/gecmis.json
```

`gol/` klasörü, `Okira59/gol` deposundaki `fs_collect.py`, `kupon.py`, `skor.py`, `leagues.py` modüllerinin kopyasıdır
(Flashscore/oran çekme, takım adı eşleştirme, skor olasılıkları). `toto.py` bunları buradan import eder.

## Otomatik çalışma ve panel
- `.github/workflows/toto.yml` her saat tetiklenir, 3 saatte bir gerçekten çalışır (elle: Actions → "Spor Toto Analiz" → Run workflow).
- Panel (GitHub Pages, `main` dalı `/docs`): https://okira59.github.io/toto/
- Android uygulaması: `docs/SporTotoAnaliz.apk`.
