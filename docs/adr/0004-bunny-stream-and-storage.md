---
status: accepted
---

# 0004: Bunny Stream and Bunny Storage for Video Delivery and Piracy Deterrence

Recorded lessons are hosted on **Bunny Stream** (HLS streaming with MediaCage DRM and signed token authentication), and PDF attachments/images are hosted on **Bunny Storage + CDN** (short-lived signed URLs for paid files). Teachers upload media directly from the browser to Bunny so large files never transit the NestJS API.

## Considered Options

- **VdoCipher**: Offers full Widevine/FairPlay hardware DRM, but is significantly more expensive per GB and per seat for an early-stage Egyptian marketplace where video bandwidth is the dominant variable cost.
- **Mux**: Strong developer experience, but higher per-minute encoding/delivery pricing and lacks built-in MediaCage-style DRM at comparable MENA pricing.
- **Self-hosted FFmpeg + object storage**: High operational overhead, poor MENA edge latency, and weak piracy protection.

## Consequences

- Consolidates video streaming and file storage under one low-cost vendor with strong Middle East edge latency.
- Browser-based MediaCage DRM is weaker than native in-app hardware DRM, so piracy deterrence is layered: signed expiring tokens + dynamic moving watermark (verified phone number only) + 2-device limit + single concurrent playback session + per-video view limit (default 4 views, counted at ~70% watched).
- Native mobile apps in Phase 2 can layer stronger in-app DRM on top of the same API if piracy pressure warrants it.
- Video uploads bypass our API server, protecting Heroku Basic dyno memory (512 MB RAM) and connection limits.
