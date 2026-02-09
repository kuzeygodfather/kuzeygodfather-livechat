# LiveChat Analiz Botu

## 🎯 Proje Hakkında

LiveChat API'sini dinleyen, analiz eden ve Telegram'a bildirim gönderen otomatik bot.

## 🔧 Özellikler

### 1. Dil ve Üslup Uyumu
- Script / standart metinlere uyum
- Yasaklı kelime ve ifade kontrolü
- Resmi-samimi ton dengesi
- Kopyala-yapıştır / ezber mesaj tespiti

### 2. Chat Kalite
- Mesajın soruya gerçekten cevap verip vermediği
- Oyalama, geçiştirme, konuyu kapatma tespiti
- Gereksiz uzatma / kısa kesme analizi
- Müşteri memnuniyetine etkisi (pozitif / nötr / negatif)

### 3. Süre ve Performans
- İlk yanıt süresi
- Çözüm süresi
- Sohbetin gereksiz uzadığı anlar
- SLA ihlali olan chat'ler

### 4. Personel Bazlı Hata Analizi
- Hangi personel hangi konuda hata yapıyor
- Aynı hatanın tekrarlanıp tekrarlanmadığı
- Uyarıya rağmen devam eden davranışlar
- Eğitim gerektiren başlıkların otomatik tespiti

### 5. Konu & Yetkinlik Haritalama
- Hangi personel hangi konularda güçlü
- Hangi konularda zorlanıyor
- Yanlış yönlendirme / eksik bilgi tespiti

### 6. Yönetici Çıktıları
- Personel kalite skoru
- Riskli personel listesi (sürekli hata yapanlar)
- İyileşen / gerileyen performans trendi
- Günlük – haftalık – aylık özet raporlar

## 🚀 Kurulum

### Gereksinimler
- Python 3.x
- `requests` kütüphanesi
- LiveChat API Key
- Telegram Bot Token

### Kurulum Adımları
```bash
# Repository'yi klonla
git clone https://github.com/kuzeygodfather/kuzeygodfather-livechat.git

# Sanal ortam oluştur
cd kuzeygodfather-livechat
python3 -m venv venv

# Aktif et
source venv/bin/activate

# Gereksinimleri kur
pip install -r requirements.txt

# API key'leri ayarla
export LIVECHAT_API_KEY="sizin_api_keyiniz"
export TELEGRAM_BOT_TOKEN="sizin_bot_tokenunuz"
```

## 📊 API Endpoint'leri

### LiveChat API
- **Base URL:** `https://livechat.systemtest.store/api/v1`
- **Endpoint:** `/chats`
- **Method:** `GET`

### Telegram Bot API
- **Base URL:** `https://api.telegram.org`
- **Endpoint:** `/bot{token}/sendMessage`
- **Method:** `POST`

## 🤖 Botun Çalışma Mantığı

```
1. LiveChat API'den verileri çek (GET /chats)
2. Her chat'ı analiz et (Dil, Hata, Performans)
3. Kritik durum tespit et (Missed, Süre aşımı, SLA ihlali)
4. Telegram'a bildirim gönder (Kritik durumlar)
5. Yönetici raporları hazırla (Günlük, Haftalık, Aylık)
```

## 📋 Rapor Formatı

```json
{
  "tarih": "2026-02-07",
  "agent_performans": {
    "Ela": {"skor": 8.5, "missed_rate": "%15", "yanit_suresi": "3.4 dk"},
    "Ayla": {"skor": 7.2, "missed_rate": "%12", "yanit_suresi": "5.1 dk"},
    "Deren": {"skor": 8.1, "missed_rate": "%10", "yanit_suresi": "4.3 dk"},
    "Asya": {"skor": 7.5, "missed_rate": "%25", "yanit_suresi": "4.5 dk"}
  },
  "kritik_durum": {
    "missed_uyari": true,
    "sure_asimi": true,
    "personel_hata": true
  },
  "trend": "Artış"
}
```

## 📄 Lisans

MIT Lisansı

## 👥 Ekip

- **Geliştirici:** Beyazıt Karaçelebi
- **AI Asistan:** Toktamış AI
- **GitHub:** kuzeygodfather
