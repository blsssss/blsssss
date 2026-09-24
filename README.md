<img src="assets/banner.png" alt="EasyMythic, jimichi, anaba" width="100%">

### Igor Iurtaev

DevOps engineer · Information security at MTUCI, Moscow<br>
[LinkedIn](https://www.linkedin.com/in/syncsyncsync/) · Discord `._sync`

#### DevOps · Sber, Quantum Technologies Center · since Sep 2026

- Network monitoring for the research lab: collectors on a Raspberry Pi behind a one-way VPN,
  PostgreSQL, five alert rules in production Grafana. Fixed the alert confirmation logic:
  on a replayed day of real data, 39 false alerts before, 0 after.
- Archive of the lab's messenger for the internal LLM: 42k messages, 3.9k threads, 7.4k attachments,
  PostgreSQL full-text and trigram search, an MCP server with 8 tools behind traefik.
  The product team started using it the day it shipped.
- Moved traefik out of the Grafana stack into its own on the shared host with about a minute
  of downtime, then migrated a live service onto it with CI deploys.

#### DevOps · fintech platform, remote · May – Sep 2026

Kubernetes, GitOps on GitLab CI, Cloudflare and Imperva in front, 350–400 RPS baseline.

- Layered L7 DDoS protection: geo filter, path allowlist, header rules, challenge on HTML only,
  separate rate limits for pages and login, edge caching. Held up against attacks of up to
  620 million requests a day. Found two bugs in the reference rule set before it went to production:
  one rule never matched, the other blocked every POST from a browser.
- Cloudflare Worker that checks captcha tokens and JWT signatures at the edge, so unauthenticated
  requests never reach the cluster. About $200 a month at full attack volume.
- Edge security review: passwords leaking into ingress logs (proven with a canary password),
  client IP spoofable through `X-Forwarded-For`, load balancers reachable around the CDN,
  secrets in the repository.
- Domain cleanup driven by ingress metrics, not by the list: two domains marked for deletion
  still served 241k and 69k API writes and were kept. Caught a stalled certificate renewal
  that reported `Ready` on a domain with 35 million requests, 25 days before TLS would fail.

<table>
<tr><td><b>Kubernetes</b></td><td>ingress-nginx · cert-manager · Kyverno · GitOps · frp reverse tunnels · PROXY protocol</td></tr>
<tr><td><b>Edge</b></td><td>Cloudflare WAF, Rate Limiting, Workers, R2, Turnstile · Imperva · CrowdSec · nginx</td></tr>
<tr><td><b>Delivery</b></td><td>GitLab CI · Docker Compose · traefik · wrangler · S3-compatible storage</td></tr>
<tr><td><b>Observability</b></td><td>Grafana alerting · Prometheus metrics · OpenTelemetry · PostgreSQL</td></tr>
<tr><td><b>Cryptography</b></td><td>AEAD · X25519 · Ed25519 · XChaCha20-Poly1305 · GOST · onion routing</td></tr>
<tr><td><b>Code</b></td><td>Go · Python · C++ · TypeScript · Bash</td></tr>
</table>

<picture>
  <source media="(prefers-color-scheme: light)" srcset="https://skillicons.dev/icons?i=kubernetes%2Cdocker%2Clinux%2Cnginx%2Ccloudflare%2Cgitlab%2Cgithubactions%2Cgrafana%2Cprometheus%2Cpostgres%2Credis%2Cgo%2Cpython%2Ccpp&theme=light">
  <img alt="Kubernetes, Docker, Linux, Nginx, Cloudflare, GitLab, GitHub Actions, Grafana, Prometheus, PostgreSQL, Redis, Go, Python, C++" src="https://skillicons.dev/icons?i=kubernetes%2Cdocker%2Clinux%2Cnginx%2Ccloudflare%2Cgitlab%2Cgithubactions%2Cgrafana%2Cprometheus%2Cpostgres%2Credis%2Cgo%2Cpython%2Ccpp&theme=dark">
</picture>

### Projects

<table>
<tr>
<td width="50%" valign="top">
<img src="assets/easymythic.png" width="64" align="left">
<b>EasyMythic</b> <sub><code>private</code></sub><br>
Mythic+ route planner for World of Warcraft. Pulls top runs from WarcraftLogs, maps noisy
combat-log enemies to dungeon positions with the Hungarian algorithm, exports routes to MDT.<br>
<sub>Go · Gin · PostgreSQL · Redis · React · Leaflet</sub>
</td>
<td width="50%" valign="top">
<img src="assets/jimichi.png" width="64" align="left">
<a href="https://github.com/blsssss/jimichi"><b>jimichi</b></a><br>
Messenger with metadata protection: three relays, nested encryption, fixed 512-byte cells,
cover traffic, keys in locked memory outside the Go heap. Includes a traffic-correlation attack to measure it.<br>
<sub>Go · X25519 · XChaCha20-Poly1305 · Kubernetes</sub>
</td>
</tr>
<tr>
<td valign="top">
<img src="assets/anaba.png" width="64" align="left">
<b>anaba</b> <sub><code>private</code></sub><br>
Aggregator for Japanese underground and archive fashion: one live feed across Mercari, Yahoo! Auctions,
Rakuma and Wunderwelt, 80+ brands, sold-price history, fake-risk flags.<br>
<sub>Go · PostgreSQL · SSE · React</sub>
</td>
<td valign="top">
<img src="assets/mylovelyvn.png" width="64" align="left">
<a href="https://github.com/blsssss/mylovelyvn"><b>MyLovelyVN</b></a><br>
Reading assistant for Japanese visual novels: captures text from the game process, splits it
into morphemes, streams a translation, two-level cache.<br>
<sub>Go · Wails · React · SQLite</sub>
</td>
</tr>
<tr>
<td valign="top">
<img src="assets/oracle.png" width="64" align="left">
<b>Oracle DBA agent</b> <sub><code>private</code></sub><br>
LLM agent that administers Oracle Database: writes and runs SQL, fixes ORA- errors, solves CTF
tasks. 1,000 traces collected, model fine-tuned on the successful ones with QLoRA.<br>
<sub>Python · Ollama · Oracle 26ai · QLoRA</sub>
</td>
<td valign="top">
<img src="assets/polycopy.png" width="64" align="left">
<b>polycopy</b> <sub><code>private</code></sub><br>
Copy-trading bot for Polymarket: fractional Kelly bet sizing, volatility, slippage and daily
loss limits, terminal UI.<br>
<sub>Go · PostgreSQL · Redis · Bubble Tea</sub>
</td>
</tr>
<tr>
<td valign="top">
<img src="assets/mzakon.png" width="64" align="left">
<a href="https://github.com/blsssss/mzakon"><b>MZakon</b></a><br>
Legal reference for GTA5 RP government factions: 1,400+ articles, step-by-step procedures,
Windows overlay and iPhone app.<br>
<sub>Python · Flutter</sub>
</td>
<td valign="top">
<img src="assets/anachan.png" width="64" align="left">
<a href="https://github.com/blsssss/anachan-public"><b>Anachan</b></a><br>
UNIX log analysis with local and remote LLMs.<br>
<sub>Go · Vite · TypeScript</sub>
</td>
</tr>
</table>

Also: Telegram and MAX bots for order tracking, a Mercari watcher, an FL.ru job feed,
[ip-echo](https://github.com/blsssss/ip-echo), [booking-go](https://github.com/blsssss/booking-go),
[online-sub](https://github.com/blsssss/online-sub).

### Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-syncsyncsync-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/syncsyncsync/)
![Discord](https://img.shields.io/badge/Discord-.__sync-5865F2?style=flat-square&logo=discord&logoColor=white)
