# CLAUDE.md — NexMeet v2 (arşiv sürümü)

> 🗄️ **ARŞİV (2026-10-07):** Bu sürüm artık geliştirilmiyor. Güncel sürüm: **[SHapeloglu/nexmeet_v3](https://github.com/SHapeloglu/nexmeet_v3)** (canlı: nexmeet.powerbi.com.tr).

İkinci sürüm (2026-06-25): v1 + **join token** (1 saat), `.env` yapılandırması, MIME doğrulamalı yükleme, **TTS proxy** (`/api/tts/*`) ile ses klonlamalı TR→EN çeviri tasarımı (GPU EC2 üzerinde `nexmeet_v2-kokoro-tts-service`), Linux/Windows ajan başlatıcıları.

- GitHub: https://github.com/SHapeloglu/nexmeet_v2 — **PUBLIC repo**
- **Güncel/canlı sürüm: `/root/nexmeet` (repo `nexmeet_v3`)** — yeni geliştirme orada yapılır. Bu repo tarihsel referans.
- Mimari: `architect.md` · Görevler: `task.md` · Fikirler: `backlog.md` · Günlük: `session.md`

## Çalıştırma (yerel deneme)

```bash
./scripts/start.sh          # Windows: scripts\start.bat — venv + pip + uvicorn
# veya: cd backend && pip install -r requirements.txt && uvicorn main:app --reload --port 8000
```

## Kurallar

- Bu repoda değişiklik yapmadan önce kullanıcıya sor; düzeltmeler normalde v3'e gider.
- `uploads/` içinde 2 kullanıcı dosyası ve `backend/__pycache__` izleniyor (.gitignore içinde olmalarına rağmen).
- README EC2 IP adreslerini içeriyor (public repo).
- Public repo: kullanıcı dosyası, IP, anahtar commit etme.
