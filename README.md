# Editing Video

Agent skill for video editing: turn a long video into vertical 9:16 shorts — best moments found
automatically, captions burned in, speakers reframed — then publish to TikTok, Instagram, YouTube,
Facebook, LinkedIn, Threads and Bluesky.

Salinan dari skill [OpenShorts](https://github.com/mutonby/openshorts) (`skills/openshorts/`),
MIT License. Kredit ke [@mutonby](https://github.com/mutonby).

## Isi

| File | Isi |
|---|---|
| `SKILL.md` | Skill utama — kapan dipakai, cara connect, core loop (submit → webhook/poll → publish) |
| `reference.md` | Referensi HTTP lengkap — payload, bentuk error, opsi per endpoint |
| `README.md` | README asli dari OpenShorts (setup API key, MCP, self-host) |

## Cara pakai

Skill ini ikut standar [Agent Skill](https://github.com/agentskills/agentskills) — satu folder bisa
dipakai di Claude Code, OpenClaw, Hermes, Codex, Gemini CLI, Cursor, VS Code.

Taruh seluruh isi repo di:

```
~/.claude/skills/editing-video/     # Claude Code
$CODEX_HOME/skills/editing-video/   # Codex
$HERMES_HOME/skills/media/editing-video/   # Hermes
```

## Yang dibutuhkan

```
OPENSHORTS_API_KEY   key osk_... dari openshorts.app
```

Self-hosted tidak perlu key: endpoint yang sama ada di `http://localhost:8000`.

Biaya:
- **Gemini** — < $0.01 per video 10 menit; atau gratis pakai LLM lokal lewat `LLM_BASE_URL` (Ollama)
- **fal.ai** — ~$0.50–1.50 per AI short
- **ElevenLabs** — voiceover / dubbing, ada tier gratis
- **Upload-Post** — 10 upload gratis/bulan ke semua platform

## Dua cara jalan

| | Self-host (gratis) | Cloud (dari $12/bln) |
|---|---|---|
| Harga | Gratis selamanya, MIT | Free plan, lalu $12/bln |
| Kecepatan | 5–8 menit per video 8 menit (CPU) | ~50 detik (GPU) |
| API key | Bawa sendiri (Gemini, fal.ai, ElevenLabs) | Gemini sudah termasuk |
| Watermark | Tidak pernah | Ada di free plan |
| Auto-posting | Pakai akun Upload-Post sendiri | Sudah tersambung |

## Tiga alat di dalamnya

1. **Clip Generator** — video panjang → klip 9:16 dengan hook, skor viralitas, subtitle
2. **AI Shorts (UGC)** — video marketing dengan aktor AI, tanpa kamera
3. **YouTube Studio** — judul AI, thumbnail, deskripsi dengan timestamp

---

MIT License. Kode asli: https://github.com/mutonby/openshorts