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

## Kurulum
```bash
pip install -r requirements.txt
```

## Çalıştırma
```bash
python toto.py
```

> Not: `toto.py`, `../gol` klasöründeki `fs_collect.py`, `kupon.py`, `skor.py` modüllerini import eder
> (`Okira59/gol` deposu). Çalıştırmak için `gol` deposunu bu klasörün yanına (`../gol`) klonlayın.
> Çıktılar `../docs/toto/data/` klasörüne yazılır (eski depo düzeni: panel `Okira59/Pyhton/docs/toto/`).
