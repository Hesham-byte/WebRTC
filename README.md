# WebRTC

Visual explainer comparing two architectures:

| ❌ Wrong | ✅ Right |
|---|---|
| Media flows through the server (relay) | Server handles **signaling only** |
| High latency, server bandwidth bottleneck | Media flows **peer-to-peer** |
| Server processes all media data | Server only exchanges session metadata |

## How WebRTC works (Right)

1. **Signaling** — Peers exchange session descriptions (SDP) and ICE candidates via a server (WebSocket, HTTP, etc.).
2. **ICE / NAT Traversal** — STUN/TURN servers help peers discover their public addresses and establish a direct connection.
3. **PeerConnection** — Once connected, media (audio, video, data) flows directly between peers over SRTP/SCTP.

## Key APIs

- `RTCPeerConnection` — manages the P2P connection
- `RTCSessionDescription` — SDP offer/answer
- `RTCIceCandidate` — network candidate for ICE
- `getUserMedia()` — captures local audio/video
- `RTCDataChannel` — arbitrary data P2P

## Diagram

Open `.excalidraw` with the [Excalidraw extension](https://marketplace.visualstudio.com/items?itemName=pomdtr.excalidraw-editor) to view the architecture comparison.
