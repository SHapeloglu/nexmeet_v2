# architect.md — NexMeet v2 Mimarisi

> Güncel mimari: `/root/nexmeet/architect.md` (v3).

```
Tarayıcı (frontend/index.html + static/js/app.js) ──WS sinyalizasyon──► FastAPI backend/main.py ──► uploads/
        └──────────── WebRTC P2P medya ────────────┘                      └─ WS ajan / kontrol oturumları
Uzak PC: agent/agent.py ──WS /ws/agent/{id}──► backend
```

## Uç Noktalar

v1 uç noktaları + `/api/join-token`, `/api/tts/synthesize`, `/api/tts/voice-profile[/status]`

## Dosyalar

- `backend/main.py` — tüm API + WebSocket, durum bellekte.
- `frontend/` — tek sayfa arayüz.
- `agent/` — uzak kontrol ajanı (`agent.py`, başlatıcılar).
- `docker/` — Dockerfile + compose; `scripts/start.*` — yerel başlatma.

## Sürüm Zinciri

v1 (temel konferans + uzak kontrol) → v2 (token, .env, TTS proxy, GPU TTS servisi) → v3 (canlı; Kokoro CPU TTS, ajan token doğrulama, dosya TTL).
