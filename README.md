# ALICE-Media-Pipeline

Unified media processing — encode, stream, synthesize, render

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum |

## ALICE Crate Integration

alice-codec, alice-streaming-protocol, alice-voice, alice-synth, alice-view

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST` | `/api/v1/encode` | メディアエンコード（動画/音声） |
| `POST` | `/api/v1/stream` | ストリーミングセッション開始 |
| `POST` | `/api/v1/synthesize` | 音声合成 |
| `POST` | `/api/v1/transcode` | フォーマット変換 |
| `GET ` | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
